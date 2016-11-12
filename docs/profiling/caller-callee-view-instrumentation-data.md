---
title: "Caller-Callee View - Instrumentation Data | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Caller/Callee view"
ms.assetid: 0908d354-aa5c-4518-8631-e25b8e7649e5
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Caller/Callee View - Instrumentation Data
The Caller/Callee view displays profiling information about a selected function and its parent and child functions in the call tree. The Caller/Callee view contains three grids.  
  
 **Current function** is displayed in the middle grid, and it shows profiling information about the selected function. The values include all calls to the function.  
  
 **Functions that called the current function** is displayed in the top grid, and it shows profiling information about the caller (parent) functions of the selected function. The values indicate the amount of the value of the current function that was generated by calls from this caller function.  
  
 **Functions that were called by the current function** is displayed in the bottom grid, and it shows profiling information about instances of the callee (child) functions of the selected function. The values indicate only the time that was spent in the child function when it was called by the current function.  
  
## General  
 The general columns identify the function in a view row.  
  
|Column|Description|  
|------------|-----------------|  
|**Function Name**|The name of the function.|  
|**Function Address**|The address of the function.|  
|**Function Line Number**|The line number of the start of this function in the source file.|  
|**Number of Calls**|The total number of calls made to this function.|  
|**Source File**|The source file that contains the definition for this function.|  
|**Module Name**|The name of the module that contains the function.|  
|**Module Path**|The path of the module that contains the function.|  
|**Process ID**|The process ID (PID) of the profiling run.|  
|**Process Name**|The name of the process.|  
|**Time Exclusive Probe Overhead**|The time overhead for this function that was caused by instrumentation. Probe overhead has been subtracted from all exclusive times.|  
|**Time Inclusive Probe Overhead**|The time overhead for this function and its child functions that was caused by instrumentation. Probe overhead has been subtracted from all inclusive times.|  
|**Type**|The context of the function:<br /><br /> **0** - the current function<br /><br /> **1** - a function that calls the current function<br /><br /> **2** - a function that is called by the current function<br /><br /> Only in [VSPerfReport](../profiling/vsperfreport.md) command-line reports.|  
|**Root Function Name**|The name of the current function. Only in [VSPerfReport](../profiling/vsperfreport.md) command-line reports.|  
  
## Elapsed Inclusive Values  
 Elapsed inclusive values indicate the time that a function was on the call stack. The time includes time that was spent in child functions and time that was spent in calls to the operating system, such as context switches and input/output operations.  
  
|Column|Description|  
|------------|-----------------|  
|**Elapsed Inclusive Time**|-   For the current function, the time that was spent in the function. The value includes time that was spent in child functions and in calls to the operating system, such as context switches and input/output operations.<br />-   For a caller function, the amount of the elapsed inclusive time of the current function that was generated by calls from this caller function.<br />-   For a callee function, the time that was spent in instances of this function that were generated by calls from the current function. The value includes time that was spent in child functions of the callee and in calls to the operating system, such as context switches and input/output operations.|  
|**Elapsed Inclusive Time %**|The percentage of the total elapsed inclusive time of the profiling run that was spent in the elapsed inclusive time of this function in this context.|  
|**Avg Elapsed Inclusive Time**|The average elapsed inclusive time of a call to this function in this context.|  
|**Max Elapsed Inclusive Time**|The maximum elapsed inclusive time of a call to this function in this context.|  
|**Min Elapsed Inclusive Time**|The minimum elapsed inclusive time of a call to this function in this context.|  
  
## Elapsed Exclusive Values  
 Elapsed exclusive values indicate the time that a function was directly executing at the top of the call stack. The time includes time that was spent in calls to the operating system, such as context switches and input/output operations, but it does not include time that was spent in child functions.  
  
|Column|Description|  
|------------|-----------------|  
|**Elapsed Exclusive Time**|-   For the current function, the time that was spent in the direct execution of the function. The value includes time that was spent in child functions and in calls to the operating system, such as context switches and input/output operations.<br />-   For a caller function, the amount of the elapsed exclusive time of the current function that was generated by calls from this caller function.<br />-   For a callee function, the time that was spent in instances of this function that were generated by calls from the current function. The value excludes time that was spent in child functions of the callee function, but it includes calls to the operating system, such as context switches and input/output operations.|  
|**Elapsed Exclusive Time %**|The percentage of the total elapsed exclusive time of the profiling run that was spent in the total elapsed exclusive time of this function in this context.|  
|**Avg Elapsed Exclusive Time**|The average elapsed exclusive time of a call to this function in this context.|  
|**Max Elapsed Exclusive Time**|The maximum elapsed exclusive time of a call to this function in this context.|  
|**Min Elapsed Exclusive Time**|The minimum elapsed exclusive time of a call to this function in this context.|  
  
## Application Inclusive Values  
 Application inclusive values indicate the time that a function was on the call stack. The time does not include time that was spent in calls to the operating system, such as context switches and input/output operations, but it does include time that was spent in child functions.  
  
|Column|Description|  
|------------|-----------------|  
|**Application Inclusive Time**|-   For the current function, the time that was spent in the function and its child functions. The value excludes time that was spent in calls to the operating system, such as context switches and input/output operations.<br />-   For a caller function, the amount of the application inclusive time of the current function that was generated by calls from this caller function.<br />-   For a callee function, the time that was spent in instances of this function that were generated by calls from the current function. The value includes time that was spent in child functions of the callee function, but it does not include time that was spent in calls to the operating system, such as context switches and input/output operations.|  
|**Application Inclusive Time %**|The percentage of the total elapsed inclusive time of the profiling run that was spent in the total application inclusive time of this function in this context.|  
|**Avg Application Inclusive Time**|The average application inclusive time of a call to this function in this context.|  
|**Max Application Inclusive Time**|The maximum application inclusive time of a call to this function in this context.|  
|**Min Application Inclusive Time**|The minimum application inclusive time of a call to this function in this context.|  
  
## Application Exclusive Values  
 Application exclusive values indicate the time that was spent in the function. This excludes time that was spent in child functions, and also excludes calls to the operating system, such as context switches and input/output operations.  
  
|Column|Description|  
|------------|-----------------|  
|**Application Exclusive Time**|-   For the current function, the time that was spent in the direct execution of the function. The value does not include time that was spent in child functions, nor does it include calls to the operating system, such as context switches and input/output operations.<br />-   For a caller function, the amount of the application exclusive time of the current function that was generated by calls from this caller function.<br />-   For a callee function, the time that was spent in instances of this function that were generated by calls from the current function. The value does not include time that was spent in child functions of the callee function, nor does it include calls to the operating system, such as context switches and input/output operations.|  
|**Application Exclusive Time %**|The percentage of the total elapsed exclusive time of the profiling run that was spent in the total application exclusive time of this function in this context.|  
|**Avg Application Exclusive Time**|The average application exclusive time of a call to this function in this context.|  
|**Max Application Exclusive Time**|The maximum application exclusive time of a call to this function in this context.|  
|**Min Application Exclusive Time**|The minimum application exclusive time of a call to this function in this context.|  
  
## See Also  
 [How to: Customize Report View Columns](../profiling/how-to-customize-report-view-columns.md)   
 [Caller / Callee View - Sampling Data](../profiling/caller-callee-view-sampling-data.md)   
 [Caller/Callee View - .NET Memory Sampling Data](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Caller/Callee View - NET Memory Instrumentation Data](../profiling/caller-callee-view-net-memory-instrumentation-data.md)