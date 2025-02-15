---
title: "Find Text, Numbers, or Dates in a Report | Microsoft Docs"
description: Learn how to use Reporting Services to search for content in a report, such as text, numbers, and dates.
ms.date: 03/07/2017
ms.prod: reporting-services
ms.technology: reports


ms.topic: conceptual
helpviewer_keywords: 
  - "searching reports"
ms.assetid: 309dffe5-00f5-404f-bb63-9e6046253ae0
author: maggiesMSFT
ms.author: maggies
---
# Find Text, Numbers, or Dates in a Report
  You can search for content in a report by typing a word or phrase that you want to find (the maximum value of a search term is 256 characters). Search is a navigation technique that finds a matching value in the report and puts focus on the part of the report that contains that value.  
  
 Search is case-insensitive and begins at the page or section that is currently selected. Only content that is visible in the report is included in the search operation. If the report contains areas that you expand or collapse, values that are in a collapsed area are skipped during the search. You can only search for text, numbers, or dates that are in the current report. If you are using an autogenerated clickthrough report to explore data, you cannot search for a term that you saw on a previously generated report, nor can you use search to find a term that might appear in a report further down the data path.  
  
 When entering a value to search on, type the value as you expect it to appear in the report. Do not pose a question, such as "what is the average profit for this month," unless you expect every word in the sentence to be in the report.  
  
 You can only search for one term or value at a time. You cannot use search operators (such as AND or OR), or symbols and wildcards. You cannot perform a search on a cross-section of the data (for example, searching for net sales for specific month for a particular product). For that kind of analysis, use Report Builder to create or use clickthrough reports.  
  
 Database and model security settings that restrict access to report data apply to search operations. If you are searching for a value in a clickthrough report that uses a model as a data source, and you do not have access to part of the model, data that is represented by the part of the model will be excluded from the search.  
  
### To find data in a report  
  
1.  Open the report.  
  
2.  In the report toolbar, enter the text, number, or date that you want to find.  
  
     If the report toolbar is not visible, it has been hidden on purpose and you cannot use the functionality it provides. Properties on the Report Viewer Web Part determine whether the toolbar is visible.  
  
3.  Click **Find**.  
  
4.  To search for subsequent occurrences of the same value, click **Next**.  
  
## See Also  
 [Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](../../reporting-services/report-server-sharepoint/add-the-report-viewer-web-part-to-a-web-page.md)  
  
  
