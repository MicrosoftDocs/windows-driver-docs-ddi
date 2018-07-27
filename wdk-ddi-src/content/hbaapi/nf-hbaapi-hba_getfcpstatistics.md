---
UID: NF:hbaapi.HBA_GetFCPStatistics
title: HBA_GetFCPStatistics function
author: windows-driver-content
description: The HBA_GetFCPStatistics routine retrieves traffic statistics that the fibre channel protocol (FCP) has collected for the indicated logical unit.
old-location: storage\hba_getfcpstatistics.htm
tech.root: storage
ms.assetid: 62ef9d02-3a59-4d4e-a48f-21a8bb4f6e58
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetFCPStatistics, HBA_GetFCPStatistics routine [Storage Devices], fibreHBA_rtns_59fb5caf-3df0-4c87-902c-6832645895d1.xml, hbaapi/HBA_GetFCPStatistics, storage.hba_getfcpstatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetFCPStatistics
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetFCPStatistics function


## -description


The <b>HBA_GetFCPStatistics</b> routine retrieves traffic statistics that the fibre channel protocol (FCP) has collected for the indicated logical unit. 


## -parameters




### -param Handle

TBD


### -param Lunit

TBD


### -param Statistics

TBD




#### - handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


#### - lunit [in]

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a> that contains information used by the operating system to identify a SCSI logical unit. 


#### - statistics [out]

Contains, on return, a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556051">HBA_FC4Statistics</a> that holds the traffic statistics that the FCP protocol has collected for the indicated logical unit. 


## -returns



The <b>HBA_GetFCPStatistics</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFCPStatistics</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the FCP statistics were successfully retrieved for the HBA referenced by <i>handle</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_INVALID_LUN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> is not attached to the logical unit referenced by <i>lunit</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_UNSUPPORTED_FC4</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not support FCP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the statistics. 

</td>
</tr>
</table>
 




## -remarks



Statistics counters in HBA_FC4Statistics are 64-bit signed integers that wrap to zero on exceeding 2**63-1. If an HBA does not support a specific statistic, it returns a value with every bit set to 1 for that statistic. For an explanation of how the counter values are determined, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556051">HBA_FC4Statistics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a>
 

 

