---
UID: NC:netdispumdddi.PFN_REPORT_STATISTIC
title: PFN_REPORT_STATISTIC (netdispumdddi.h)
description: Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is PFN_REPORT_STATISTIC.
old-location: display\reportstatistic.htm
tech.root: display
ms.assetid: 13e1afa2-5552-468f-ac6b-3458dedd9b76
ms.date: 05/10/2018
keywords: ["PFN_REPORT_STATISTIC callback function"]
ms.keywords: PFN_REPORT_STATISTIC, PFN_REPORT_STATISTIC callback, ReportStatistic, ReportStatistic callback function [Display Devices], display.reportstatistic, netdispumdddi/ReportStatistic
f1_keywords:
 - "netdispumdddi/ReportStatistic"
 - "ReportStatistic"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- ReportStatistic
targetos: Windows
req.typenames: 
---

# PFN_REPORT_STATISTIC callback function


## -description


Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is <b>PFN_REPORT_STATISTIC</b>.




## -parameters




### -param hMiracastDeviceHandle 
[in]
A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.


### -param pStatistics 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_statistic_data">MIRACAST_STATISTIC_DATA</a> structure that contains the statistics data.


## -remarks



When the operating system calls this function, it logs the data from the <i>pStatistics</i> parameter but takes no other action.

For more info on how to use this function, see these topics:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/display/miracast-user-mode-driver-tasks-to-support-miracast-wireless-displays">Miracast user-mode driver tasks to support Miracast wireless displays</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/display/reporting-miracast-encode-chunks-and-statistics">Reporting Miracast encode chunks and statistics</a>
</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_statistic_data">MIRACAST_STATISTIC_DATA</a>
 

 

