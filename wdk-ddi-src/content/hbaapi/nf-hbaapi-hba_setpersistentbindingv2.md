---
UID: NF:hbaapi.HBA_SetPersistentBindingV2
title: HBA_SetPersistentBindingV2 function
author: windows-driver-content
description: The HBA_SetPersistentBindingV2 routine establishes a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that the HBA can enumerate on the specified port.
old-location: storage\hba_setpersistentbindingv2.htm
old-project: storage
ms.assetid: b0b32954-62d1-4434-892f-67106b0f8ef7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_SetPersistentBindingV2, HBA_SetPersistentBindingV2 routine [Storage Devices], fibreHBA_rtns_b081179f-690d-4646-ae40-1737c5933394.xml, hbaapi/HBA_SetPersistentBindingV2, storage.hba_setpersistentbindingv2
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
-	HBA_SetPersistentBindingV2
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_SetPersistentBindingV2 function


## -description


The <b>HBA_SetPersistentBindingV2</b> routine establishes a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that the HBA can enumerate on the specified port.


## -syntax


````
HBA_STATUS HBA_API HBA_SetPersistentBindingV2(
  _In_ HBA_HANDLE       Handle,
  _In_ HBA_WWN          HbaPortWWN,
  _In_ PHBA_FCPBINDING2 Binding
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port referenced by <i>HbaPortWWN </i>is located. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the port that enumerates the logical units specified by the persistent bindings. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param Binding [in]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbinding2.md">HBA_FCPBinding2</a> that holds an array of elements of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry2.md">HBA_FCPBindingEntry2</a>, each of which holds a persistent binding between operating system and fibre channel protocol (FCP) identifiers for a logical unit. On input, the <b>NumberOfEntries</b> member of HBA_FCPBinding2 should contain the number of bindings that fit in the output buffer. On output, <b>NumberOfEntries</b> holds the number of bindings actually returned, which is equal to the number specified on input or the full set of available bindings, whichever is smaller. The value in <b>NumberOfEntries</b> will contain the number of persistent bindings returned even when an error occurred because of insufficient buffer space. 

On output, the <b>Status</b> member of each HBA_FCPBindingEntry2 structure is 0. 


## -returns



The <b>HBA_SetBindingSupport2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SetBindingSupport2</b> returns one of the following values.

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
Returned if one or more of the persistent bindings were successfully established. Each requested binding can succeed or fail independently of the others. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter referenced by <i>handle </i>does not support persistent bindings. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the routine from associating any of the specified persistent bindings with the port. 

</td>
</tr>
</table>
 




## -remarks



The <b>HBA_SetPersistentBindingV2</b> routine establishes a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that the HBA, referenced by <i>HbaHandle, </i>can enumerate on the port specified by <i>HbaPortWWN</i>. The bindings that <b>HBA_SetPersistentBindingV2</b> establishes persist across reboots of the operating system. 




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_getpersistentbindingv2.md">HBA_GetPersistentBindingV2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SetPersistentBindingV2 routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

