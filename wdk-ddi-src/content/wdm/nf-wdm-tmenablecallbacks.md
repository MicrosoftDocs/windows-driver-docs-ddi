---
UID: NF:wdm.TmEnableCallbacks
title: TmEnableCallbacks function
author: windows-driver-content
description: The TmEnableCallbacks routine enables a callback routine that receives transaction notifications.
old-location: kernel\tmenablecallbacks.htm
old-project: kernel
ms.assetid: d3f79cda-349a-4a42-a2a9-d9be3a695c1c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmEnableCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TmEnableCallbacks
req.alt-loc: NtosKrnl.exe,Ext-MS-Win-ntos-tm-l1-1-0.dll,tm.sys
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmEnableCallbacks function



## -description
The <b>TmEnableCallbacks</b> routine enables a callback routine that receives <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">transaction notifications</a>. 



## -syntax

````
NTSTATUS TmEnableCallbacks(
  _In_     PKRESOURCEMANAGER   ResourceManager,
  _In_     PTM_RM_NOTIFICATION CallbackRoutine,
  _In_opt_ PVOID               RMKey
);
````


## -parameters

### -param ResourceManager [in]

A pointer to a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>. To obtain this pointer, your component must call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a> or <a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a> provided.


### -param CallbackRoutine [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> routine.


### -param RMKey [in, optional]

A caller-defined context value that uniquely identifies the resource manager. The caller's <i>ResourceManagerNotification</i> routine receives this value as input.


## -returns
<b>TmEnableCallbacks</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value:
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The <i>CallbackRoutine</i> pointer is <b>NULL</b>.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
Your resource manager can call <b>TmEnableCallbacks</b> to enable a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Use <b>TmEnableCallbacks</b> to enable asynchronous notifications. Use <a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a> to obtain notifications synchronously. 

Resource managers can register one callback routine for each resource manager object.

For more information about the <b>TmEnableCallbacks</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>. 

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmEnableCallbacks routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

