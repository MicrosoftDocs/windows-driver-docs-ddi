---
UID: NF:hbaapi.HBA_GetPersistentBindingV2
title: HBA_GetPersistentBindingV2 function
author: windows-driver-content
description: The HBA_GetPersistentBindingV2 routine retrieves persistent bindings, including extended bindings, for logical units that the HBA enumerates on the indicated port.
old-location: storage\hba_getpersistentbindingv2.htm
old-project: storage
ms.assetid: 549edba4-8622-4117-b013-bcaf1787e8b4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetPersistentBindingV2, HBA_GetPersistentBindingV2 routine [Storage Devices], fibreHBA_rtns_b3906ad3-bbf6-43b4-b427-9276870645cd.xml, hbaapi/HBA_GetPersistentBindingV2, storage.hba_getpersistentbindingv2
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
-	HBA_GetPersistentBindingV2
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetPersistentBindingV2 function


## -description


The <b>HBA_GetPersistentBindingV2</b> routine retrieves persistent bindings, including extended bindings, for logical units that the HBA enumerates on the indicated port. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetPersistentBindingV2(
  _In_    HBA_HANDLE       HbaHandle,
  _In_    HBA_WWN          HbaPortWWN,
  _Inout_ PHBA_FCPBINDING2 Binding
);
````


## -parameters




### -param Handle

TBD


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the fibre channel port on which the logical units are enumerated. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param Binding [in, out]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbinding2.md">HBA_FCPBinding2</a> that holds an array of elements of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry2.md">HBA_FCPBindingEntry2</a>, each of which holds a persistent binding between operating system and fibre channel protocol (FCP) identifiers for a logical unit. On input, the <b>NumberOfEntries</b> member of HBA_FCPBinding2 should contain the number of bindings that fit in the output buffer. On output, <b>NumberOfEntries</b> holds the number of bindings actually returned, which is equal to the number specified on input, or the full set of available bindings, whichever is smaller. The value in <b>NumberOfEntries</b> contains the number of persistent bindings returned even when an error occurred because of insufficient buffer space. 

On output, the <b>Status</b> member of each HBA_FCPBindingEntry2 structure is 0. 


#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the persistent bindings. The HBA returns bindings for the logical units that it can enumerate on the port specified by <i>HbaPortWWN</i>. 


## -returns



The <b>HBA_GetPersistentBindingV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetPersistentBindingV2</b> returns one of the following qualifiers.

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
Returned if the persistent bindings were successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>HbaHandle</i> does not contain a port with the name specified in <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter referenced by <i>HbaHandle </i>does not support persistent binding. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_MORE_DATA</b></dt>
</dl>
</td>
<td width="60%">
Returned if a larger buffer is required to contain binding information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the persistent bindings. 

</td>
</tr>
</table>
 




## -remarks



The <b>HBA_GetPersistentBindingV2</b> routine retrieves a set of bindings between operating system and FCP identifiers for the logical units that the HBA referenced by <i>HbaHandle </i>can enumerate on the port specified by <i>HbaPortWWN</i>. The bindings that <b>HBA_GetPersistentBindingV2</b> retrieves persist across reboots of the operating system.

This routine is similar to the <a href="..\hbaapi\nf-hbaapi-hba_getfcppersistentbinding.md">HBA_GetFcpPersistentBinding</a> routine. The key difference is that the bindings that <b>HBA_GetPersistentBindingV2</b> returns include a logical unit ID descriptor (LUID) derived from vital product data retrieved with a SCSI inquiry command. If the vital product data for a logical unit provides more than one LUID, then the LUID that <b>HBA_GetPersistentBindingV2</b> returns depends on the types of LUIDs provided. For a complete explanation of how the LUID is chosen when more than one LUID is available, see the T11 committee's <i>Fibre Channel HBA API </i>specification.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\nf-hbaapi-hba_getfcppersistentbinding.md">HBA_GetFcpPersistentBinding</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry2.md">HBA_FCPBindingEntry2</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbinding.md">HBA_FCPBinding</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetPersistentBindingV2 routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

