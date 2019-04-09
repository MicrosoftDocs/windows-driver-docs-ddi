---
UID: NC:netdispumdddi.PFN_REPORT_STATISTIC
title: PFN_REPORT_STATISTIC (netdispumdddi.h)
description: Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is PFN_REPORT_STATISTIC.
old-location: display\reportstatistic.htm
tech.root: display
ms.assetid: 13e1afa2-5552-468f-ac6b-3458dedd9b76
ms.date: 05/10/2018
ms.keywords: PFN_REPORT_STATISTIC, PFN_REPORT_STATISTIC callback, ReportStatistic, ReportStatistic callback function [Display Devices], display.reportstatistic, netdispumdddi/ReportStatistic
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- ReportStatistic
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_REPORT_STATISTIC callback function


## -description


Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.The data type of this function is <b>PFN_REPORT_STATISTIC</b>.




## -parameters




### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -param *pStatistics [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265479">MIRACAST_STATISTIC_DATA</a> structure that contains the statistics data.


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




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265479">MIRACAST_STATISTIC_DATA</a>
 

 

