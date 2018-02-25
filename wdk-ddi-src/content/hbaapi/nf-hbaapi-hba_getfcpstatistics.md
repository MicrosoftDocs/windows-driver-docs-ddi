---
UID: NF:hbaapi.HBA_GetFCPStatistics
title: HBA_GetFCPStatistics function
author: windows-driver-content
description: The HBA_GetFCPStatistics routine retrieves traffic statistics that the fibre channel protocol (FCP) has collected for the indicated logical unit.
old-location: storage\hba_getfcpstatistics.htm
old-project: storage
ms.assetid: 62ef9d02-3a59-4d4e-a48f-21a8bb4f6e58
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, B, C, F, G, H, HBA_GetFCPStatistics, HBA_GetFCPStatistics routine [Storage Devices], P, S, _, a, c, e, fibreHBA_rtns_59fb5caf-3df0-4c87-902c-6832645895d1.xml, hbaapi/HBA_GetFCPStatistics, i, s, storage.hba_getfcpstatistics, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetFCPStatistics
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetFCPStatistics function


## -description


The <b>HBA_GetFCPStatistics</b> routine retrieves traffic statistics that the fibre channel protocol (FCP) has collected for the indicated logical unit. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetFCPStatistics(
  _In_        HBA_HANDLE        handle,
  _In_  const HBA_SCSIID        *lunit,
  _Out_       HBA_FC4STATISTICS *statistics
);
````


## -parameters




### -param Handle

TBD


### -param Lunit

TBD


### -param Statistics

TBD




#### - handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


#### - lunit [in]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a> that contains information used by the operating system to identify a SCSI logical unit. 


#### - statistics [out]

Contains, on return, a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a> that holds the traffic statistics that the FCP protocol has collected for the indicated logical unit. 


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

<a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFCPStatistics routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

