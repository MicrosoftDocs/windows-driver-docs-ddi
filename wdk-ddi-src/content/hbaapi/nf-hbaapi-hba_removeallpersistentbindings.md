---
UID: NF:hbaapi.HBA_RemoveAllPersistentBindings
title: HBA_RemoveAllPersistentBindings function
author: windows-driver-content
description: The HBA_RemoveAllPersistentBindings routine removes all persistent bindings for a specified HBA port.
old-location: storage\hba_removeallpersistentbindings.htm
old-project: storage
ms.assetid: f15823dd-a9c5-46a8-a376-41b831450b66
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_RemoveAllPersistentBindings, HBA_RemoveAllPersistentBindings routine [Storage Devices], fibreHBA_rtns_1b72392e-f155-41aa-915a-a39da952afec.xml, hbaapi/HBA_RemoveAllPersistentBindings, storage.hba_removeallpersistentbindings
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
-	HBA_RemoveAllPersistentBindings
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RemoveAllPersistentBindings function


## -description


The <b>HBA_RemoveAllPersistentBindings</b> routine removes all persistent bindings for a specified HBA port.


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port for which to remove all persistent bindings. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


## -returns



The <b>HBA_RemoveAllPersistentBindings</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RemoveAllPersistentBindings</b> returns one of the following values.

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
Returned if all persistent bindings were successfully removed for the indicated port. 

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

