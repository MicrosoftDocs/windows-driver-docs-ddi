---
UID: NF:hbaapi.HBA_RemovePersistentBinding
title: HBA_RemovePersistentBinding function
author: windows-driver-content
description: The HBA_RemovePersistentBinding routine retrieves information about the specified target.
old-location: storage\hba_removepersistentbinding.htm
old-project: storage
ms.assetid: f2dbdd95-ddf9-4e95-acd5-853c29cebf02
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hba_removepersistentbinding, hbaapi/HBA_RemovePersistentBinding, HBA_RemovePersistentBinding, HBA_RemovePersistentBinding routine [Storage Devices], fibreHBA_rtns_d8ccc5eb-b268-4809-88e5-3cee263f6b35.xml
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
-	HBA_RemovePersistentBinding
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RemovePersistentBinding function


## -description


The <b>HBA_RemovePersistentBinding</b> routine retrieves information about the specified target.


## -syntax


````
HBA_STATUS HBA_API HBA_RemovePersistentBinding(
  _In_ HBA_HANDLE       Handle,
  _In_ HBA_WWN          HbaPortWWN,
  _In_ PHBA_FCPBINDING2 Binding
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port for which to remove all persistent bindings. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param Binding [in]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbinding2.md">HBA_FCPBinding2</a> that contains an array of bindings between operating system identifiers, SCSI logical unit ID descriptors (LUIDs) and fibre channel protocol (FCP) identifiers for a set of logical units. 


## -returns



The <b>HBA_RemovePersistentBinding</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RemovePersistentBinding</b> returns one of the following values.

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
Returned if the indicated persistent bindings were successfully removed for the indicated port. 

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
Returned if the HBA referenced by <i>handle</i> does not support persistent bindings.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the removal of the persistent bindings. 

</td>
</tr>
</table>
 




## -remarks



The removal of persistent bindings does not change target mappings until the operating system is restarted or HBA and/or fabric is reinitialized. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RemovePersistentBinding routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

