---
UID: NC:netdispumdddi.PFN_REPORT_STATISTIC
title: PFN_REPORT_STATISTIC
author: windows-driver-content
description: Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is PFN_REPORT_STATISTIC.
old-location: display\reportstatistic.htm
old-project: display
ms.assetid: 13e1afa2-5552-468f-ac6b-3458dedd9b76
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.reportstatistic, PFN_REPORT_STATISTIC, ReportStatistic callback function [Display Devices], ReportStatistic, PFN_REPORT_STATISTIC, PFN_REPORT_STATISTIC, netdispumdddi/ReportStatistic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Netdispumdddi.h
apiname:
-	ReportStatistic
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_REPORT_STATISTIC callback


## -description


Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is <b>PFN_REPORT_STATISTIC</b>.




## -prototype


````
PFN_REPORT_STATISTIC ReportStatistic;

VOID ReportStatistic(
  _In_ HANDLE                  hMiracastDeviceHandle,
  _In_ MIRACAST_STATISTIC_DATA *pStatistics
)
{ ... }
````


## -parameters




#### - hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


#### - *pStatistics [in]

A pointer to a <a href="..\netdispumdddi\ns-netdispumdddi-miracast_statistic_data.md">MIRACAST_STATISTIC_DATA</a> structure that contains the statistics data.


#### - pStatistics [in]

A pointer to a <a href="..\netdispumdddi\ns-netdispumdddi-miracast_statistic_data.md">MIRACAST_STATISTIC_DATA</a> structure that contains the statistics data.


## -returns


Does not return a value.



## -remarks


When the operating system calls this function, it logs the data from the <i>pStatistics</i> parameter but takes no other action.

For more info on how to use this function, see these topics:
<ul>
<li>
<a href="https://msdn.microsoft.com/FF5D7760-2407-487A-8363-7AC3B6385F6C">Miracast user-mode driver tasks to support Miracast wireless displays</a>
</li>
<li>
<a href="https://msdn.microsoft.com/E1CE637F-42ED-4BEB-A2FF-04B4B88469DC">Reporting Miracast encode chunks and statistics</a>
</li>
</ul>


## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>

<a href="..\netdispumdddi\ns-netdispumdddi-miracast_statistic_data.md">MIRACAST_STATISTIC_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_REPORT_STATISTIC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

