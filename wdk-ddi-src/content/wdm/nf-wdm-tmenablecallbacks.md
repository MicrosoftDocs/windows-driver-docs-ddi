---
UID: NF:wdm.TmEnableCallbacks
title: TmEnableCallbacks function
author: windows-driver-content
description: The TmEnableCallbacks routine enables a callback routine that receives transaction notifications.
old-location: kernel\tmenablecallbacks.htm
tech.root: kernel
ms.assetid: d3f79cda-349a-4a42-a2a9-d9be3a695c1c
ms.date: 04/30/2018
ms.keywords: TmEnableCallbacks, TmEnableCallbacks routine [Kernel-Mode Driver Architecture], kernel.tmenablecallbacks, ktm_ref_0d901be3-7a5f-4296-b0fc-b8bdf84c43ec.xml, wdm/TmEnableCallbacks
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmEnableCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmEnableCallbacks function


## -description


The <b>TmEnableCallbacks</b> routine enables a callback routine that receives <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">transaction notifications</a>. 


## -parameters




### -param ResourceManager [in]

A pointer to a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a> provided.


### -param CallbackRoutine [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> routine.


### -param RMKey [in, optional]

A caller-defined context value that uniquely identifies the resource manager. The caller's <i>ResourceManagerNotification</i> routine receives this value as input.


## -returns



<b>TmEnableCallbacks</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The <i>CallbackRoutine</i> pointer is <b>NULL</b>.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Your resource manager can call <b>TmEnableCallbacks</b> to enable a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Use <b>TmEnableCallbacks</b> to enable asynchronous notifications. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a> to obtain notifications synchronously. 

Resource managers can register one callback routine for each resource manager object.

For more information about the <b>TmEnableCallbacks</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>. 

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>
 

 

