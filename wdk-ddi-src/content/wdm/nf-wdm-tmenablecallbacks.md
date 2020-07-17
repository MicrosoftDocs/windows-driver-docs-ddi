---
UID: NF:wdm.TmEnableCallbacks
title: TmEnableCallbacks function (wdm.h)
description: The TmEnableCallbacks routine enables a callback routine that receives transaction notifications.
old-location: kernel\tmenablecallbacks.htm
tech.root: kernel
ms.assetid: d3f79cda-349a-4a42-a2a9-d9be3a695c1c
ms.date: 04/30/2018
keywords: ["TmEnableCallbacks function"]
ms.keywords: TmEnableCallbacks, TmEnableCallbacks routine [Kernel-Mode Driver Architecture], kernel.tmenablecallbacks, ktm_ref_0d901be3-7a5f-4296-b0fc-b8bdf84c43ec.xml, wdm/TmEnableCallbacks
f1_keywords:
 - "wdm/TmEnableCallbacks"
 - "TmEnableCallbacks"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ext-MS-Win-ntos-tm-l1-1-0.dll
- tm.sys
api_name:
- TmEnableCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmEnableCallbacks function


## -description


The <b>TmEnableCallbacks</b> routine enables a callback routine that receives <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-notifications">transaction notifications</a>. 


## -parameters




### -param ResourceManager [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a>. To obtain this pointer, your component must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a> provided.


### -param CallbackRoutine [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> routine.


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
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



Your resource manager can call <b>TmEnableCallbacks</b> to enable a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Use <b>TmEnableCallbacks</b> to enable asynchronous notifications. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a> to obtain notifications synchronously. 

Resource managers can register one callback routine for each resource manager object.

For more information about the <b>TmEnableCallbacks</b> routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>. 

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>
 

 

