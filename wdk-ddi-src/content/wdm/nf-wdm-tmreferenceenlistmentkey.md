---
UID: NF:wdm.TmReferenceEnlistmentKey
title: TmReferenceEnlistmentKey function (wdm.h)
description: The TmReferenceEnlistmentKey routine increments the reference count for the key of a specified enlistment object and retrieves the key.
old-location: kernel\tmreferenceenlistmentkey.htm
tech.root: kernel
ms.assetid: c4fd9a56-8743-4099-b261-43c1afc2a5f1
ms.date: 04/30/2018
ms.keywords: TmReferenceEnlistmentKey, TmReferenceEnlistmentKey routine [Kernel-Mode Driver Architecture], kernel.tmreferenceenlistmentkey, ktm_ref_9e57ee05-1004-4d3d-9fa6-9eb473057bbf.xml, wdm/TmReferenceEnlistmentKey
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
req.irql: "<= DISPATCH_LEVEL"
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
- TmReferenceEnlistmentKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmReferenceEnlistmentKey function


## -description


The <b>TmReferenceEnlistmentKey</b> routine increments the reference count for the key of a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> and retrieves the key.


## -parameters




### -param Enlistment [in]

A pointer to an enlistment object. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.


### -param Key [out]

A pointer to a variable that receives the enlistment object's enlistment key. The caller assigns an enlistment key when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>.


## -returns



<b>TmReferenceEnlistmentKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Key</i> parameter's value is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The reference count of the specified enlistment object has been decremented to zero, so the reference count cannot be incremented.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The reference count is at its maximum value (0xFFFFFFFF) and cannot be incremented.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The <b>TmReferenceEnlistmentKey</b> routine increments the reference count for an enlistment object's key value, and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmdereferenceenlistmentkey">TmDereferenceEnlistmentKey</a> routine decrements the count. 

If a resource manager has defined a key value for an enlistment, the resource manager receives the key value when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine.

While a resource manager is processing a notification, it might use the key as a pointer to a temporary memory allocation, and it might use the reference count to determine when it should deallocate the memory.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmdereferenceenlistmentkey">TmDereferenceEnlistmentKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>
 

 

