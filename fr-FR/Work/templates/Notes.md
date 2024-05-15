---
aliases: ["<% tp.file.title %>"]
---
<%*
PERIODICITY = {
    YEARLY: "yearly",
    QUARTERLY: "quarterly",
    MONTHLY: "monthly",
    WEEKLY: "weekly",
    DAILY: "daily"
}

function getPeriodicityFromFileName(fileName) {
    if (fileName.match(/^\d{4}-FY$/) != null){
        return PERIODICITY.YEARLY
    }
    if (fileName.match(/^\d{4}-Q\d$/) != null){
        return PERIODICITY.QUARTERLY
    }
    if (fileName.match(/^\d{4}-\d{2}$/) != null){
        return PERIODICITY.MONTHLY
    }
    if (fileName.match(/^\d{4}-\d{2}-\d{2}-to-\d{4}-\d{2}-\d{2}$/) != null){
        return PERIODICITY.WEEKLY
    }
    if (fileName.match(/^\d{4}-\d{2}-\d{2}$/) != null){
        return PERIODICITY.DAILY
    }

    throw new Error(`Cannot infer periodicity of the note (daily, weekly, ...) from the file name '${fileName}'`)
}

function generatePreSummaryContent(periodicity){
    if (periodicity == PERIODICITY.DAILY) {
        const filedate = tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD")
        const week = tp.date.weekday("YYYY-MM-DD", 1, filedate, "YYYY-MM-DD") + "-to-" + tp.date.weekday("YYYY-MM-DD", 5, filedate, "YYYY-MM-DD")
        return `Semaine [[ ${week} ]]`
    }

    if (periodicity == PERIODICITY.WEEKLY) {
        const week = tp.file.title
        return `Mois [[ ${week.substr(0,7)} ]]`
    }

    if (periodicity == PERIODICITY.MONTHLY) {
        const firstDayOfThisMonth = tp.date.now("YYYY-MM-DD", 0, tp.file.title + "-01", "YYYY-MM-DD")
        const quarter = tp.date.now("YYYY", 0, firstDayOfThisMonth) + "-Q" + tp.date.now("Q", 0, firstDayOfThisMonth)
        return `Trimestre [[ ${quarter} ]]`
    }

    if (periodicity == PERIODICITY.QUARTERLY) {
        const thisQuarter = parseInt(tp.file.title.substr(tp.file.title.length - 1))
        const thisYear = tp.file.title.substr(0,4)
        const refDateStr = "" + thisYear + "-" + (1 + (thisQuarter - 1) * 3 ) + "-01"
        const firstDayOfThisQuarter = tp.date.now("YYYY-MM-DD", 0, refDateStr, "YYYY-MM-DD")
        return `Année [[ ${thisYear}-FY ]]`
    }

    return ""
}

function generateDetailsContent(periodicity){

    if (periodicity == PERIODICITY.WEEKLY) {
        const firstDayOfThisweek = tp.date.now("YYYY-MM-DD", 0, tp.file.title.substr(0,10), "YYYY-MM-DD")
        const output = `- [[${tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek)}]]: ![[${tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek)}#Résumé]]` + 
            `\n- [[${tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek)}]]: ![[${tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek)}#Résumé]]` +
            `\n- [[${tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek)}]]: ![[${tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek)}#Résumé]]` +
            `\n- [[${tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek)}]]: ![[${tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek)}#Résumé]]` +
            `\n- [[${tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek)}]]: ![[${tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek)}#Résumé]]`
        
        return output
    }

    if (periodicity == PERIODICITY.MONTHLY) {
        const firstDayOfThisMonth = tp.date.now("YYYY-MM-DD", 0, tp.file.title + "-01", "YYYY-MM-DD")
        const weeks = [...Array(6).keys()].map(
            offset => tp.date.weekday("YYYY-MM-DD", 1 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD") + "-to-" + tp.date.weekday("YYYY-MM-DD",  5 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD")  
        )
        const output = "**Important: Il y a des lignes en trop, supprimez-les**" + 
        `\n- [[${weeks[0]}]]: ![[${weeks[0]}#Résumé]]` + 
        `\n- [[${weeks[1]}]]: ![[${weeks[1]}#Résumé]]` + 
        `\n- [[${weeks[2]}]]: ![[${weeks[2]}#Résumé]]` + 
        `\n- [[${weeks[3]}]]: ![[${weeks[3]}#Résumé]]` + 
        `\n- [[${weeks[4]}]]: ![[${weeks[4]}#Résumé]]` + 
        `\n- [[${weeks[5]}]]: ![[${weeks[5]}#Résumé]]`
        return output
    }

    if (periodicity == PERIODICITY.QUARTERLY) {
        const thisYear = tp.file.title.substr(0,4)
        const thisQuarter = parseInt(tp.file.title.substr(tp.file.title.length - 1))
        const refDateStr = "" + thisYear + "-" + (1 + (thisQuarter - 1) * 3 ) + "-01"
        const months = [...Array(3).keys()].map(
            offset => tp.date.now("YYYY-MM", "P+" + offset + "M", refDateStr)
        )
        const output = `- [[${months[0]}]]: ![[${months[0]}#Résumé]]`+
        `\n- [[${months[1]}]]: ![[${months[1]}#Résumé]]` +
        `\n- [[${months[2]}]]: ![[${months[2]}#Résumé]]`
        return output
    }

    if (periodicity == PERIODICITY.YEARLY) {
        const thisYear = tp.file.title.substr(0,4)
        const output = `- [[${thisYear}-Q1]]: ![[${thisYear}-Q1#Résumé]]` +
        `\n- [[${thisYear}-Q2]]: ![[${thisYear}-Q2#Résumé]]` +
        `\n- [[${thisYear}-Q3]]: ![[${thisYear}-Q3#Résumé]]` +
        `\n- [[${thisYear}-Q4]]: ![[${thisYear}-Q4#Résumé]]`
        return output
    }

    return ""
}

periodicity = getPeriodicityFromFileName(tp.file.title)
_%>
<% generatePreSummaryContent(periodicity) %>
## Résumé

## Détails
<% generateDetailsContent(periodicity) %>
