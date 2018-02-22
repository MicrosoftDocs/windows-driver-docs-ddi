---
UID: NF:hbaapi.HBA_GetFcpPersistentBinding
title: HBA_GetFcpPersistentBinding function
author: windows-driver-content
description: The HBA_GetFcpPersistentBinding routine retrieves the persistent bindings that are associated with the logical units that the HBA can enumerate.
old-location: storage\hba_getfcppersistentbinding.htm
old-project: storage
ms.assetid: a17a6dfa-c067-4a85-8787-ffb4fb6cb7ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: HBA_GetFcpPersistentBinding routine [Storage Devices], fibreHBA_rtns_9ab54a28-f020-426e-9ea6-2aba3666884b.xml, HBA_GetFcpPersistentBinding, storage.hba_getfcppersistentbinding, hbaapi/HBA_GetFcpPersistentBinding
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
-	HBA_GetFcpPersistentBinding
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetFcpPersistentBinding function


## -description


The <b>HBA_GetFcpPersistentBinding</b> routine retrieves the persistent bindings that are associated with the logical units that the HBA can enumerate.


## -syntax


````
HBA_STATUS HBA_API HBA_GetFcpPersistentBinding(
  _In_    HBA_HANDLE      Handle,
  _Inout_ PHBA_FCPBINDING Binding
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the bindings. The HBA returns bindings for the targets that it can enumerate. 


### -param Binding [in, out]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbinding.md">HBA_FCPBinding</a> that holds an array of elements of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry.md">HBA_FCPBindingEntry</a>, each of which holds a persistent binding between operating system and fibre channel protocol (FCP) identifiers for a logical unit. On input, the <b>NumberOfEntries</b> member of HBA_FCPBinding should contain the number of bindings that fit in the output buffer. On output, <b>NumberOfEntries</b> holds the number of entries actually returned, which is equal to the number specified on input, or the full set of available bindings, whichever is smaller. The value in <b>NumberOfEntries</b> will contain the number of persistent bindings returned even when an error occurred because of insufficient buffer space. 


## -returns



The <b>HBA_GetFcpPersistentBinding</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFcpPersistentBinding</b> returns one of the following qualifiers.

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



The <b>HBA_GetFcpPersistentBinding</b> routine retrieves a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that it can enumerate. These bindings persist across reboots of the operating system.




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbinding.md">HBA_FCPBinding</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFcpPersistentBinding routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

