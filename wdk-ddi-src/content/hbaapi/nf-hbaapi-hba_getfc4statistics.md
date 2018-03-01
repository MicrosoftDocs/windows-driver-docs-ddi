---
UID: NF:hbaapi.HBA_GetFC4Statistics
title: HBA_GetFC4Statistics function
author: windows-driver-content
description: The HBA_GetFC4Statistics routine retrieves traffic statistics that a specific FC-4 protocol has collected for the indicated port and local adapter.
old-location: storage\hba_getfc4statistics.htm
old-project: storage
ms.assetid: 9c86c753-dddf-488d-b332-4b79602c454a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetFC4Statistics, HBA_GetFC4Statistics routine [Storage Devices], fibreHBA_rtns_483a1f57-5e5b-4919-a61b-5853ffb5be6f.xml, hbaapi/HBA_GetFC4Statistics, storage.hba_getfc4statistics
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
-	HBA_GetFC4Statistics
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetFC4Statistics function


## -description


The <b>HBA_GetFC4Statistics</b> routine retrieves traffic statistics that a specific FC-4 protocol has collected for the indicated port and local adapter. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetFC4Statistics(
  _In_  HBA_HANDLE        handle,
  _In_  HBA_WWN           portWWN,
  _In_  HBA_UINT8         FC4type,
  _Out_ HBA_FC4STATISTICS *statistics
);
````


## -parameters




### -param Handle

TBD


### -param PortWWN

TBD


### -param FC4type [in]

Contains a value that indicates the type FC-4 protocol. For an explanation of FC4 types and the values that can be assigned to this parameter, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 


### -param Statistics

TBD




#### - handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


#### - portWWN [in]

Contains a 64-bit world-wide name (WWN) that uniquely identifies the local HBA port for which this routine retrieves traffic statistics for a specific FC-4 protocol. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


#### - statistics [out]

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a> that contains statistics for the specified port and FC-4 protocol. 


## -returns



The <b>HBA_GetFC4Statistics</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFC4Statistics</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter does not contain a port with the name <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter does not support the specified FC-4 protocol. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the port attributes.

</td>
</tr>
</table>
 




## -remarks



Statistics counters in <a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a> are 64-bit signed integers that wrap to zero on exceeding 2**63-1. If an HBA does not support a specific statistic, it returns a value with every bit set to 1 for that statistic. For an explanation of how the counter values are determined, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 




## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFC4Statistics routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

