---
UID: NF:wdm.TmDereferenceEnlistmentKey
title: TmDereferenceEnlistmentKey function (wdm.h)
description: The TmDereferenceEnlistmentKey routine decrements the reference count for the key of a specified enlistment object.
old-location: kernel\tmdereferenceenlistmentkey.htm
tech.root: kernel
ms.assetid: e03b5f4d-58d5-43d5-a0c3-8a3cc83bd38a
ms.date: 04/30/2018
ms.keywords: TmDereferenceEnlistmentKey, TmDereferenceEnlistmentKey routine [Kernel-Mode Driver Architecture], kernel.tmdereferenceenlistmentkey, ktm_ref_88254e83-cb2a-4da1-9216-b12314ea73ea.xml, wdm/TmDereferenceEnlistmentKey
ms.topic: function
f1_keywords:
 - "wdm/TmDereferenceEnlistmentKey"
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
req.irql: <= DISPATCH_LEVEL
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
- TmDereferenceEnlistmentKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmDereferenceEnlistmentKey function


## -description


The <b>TmDereferenceEnlistmentKey</b> routine decrements the reference count for the key of a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.


## -parameters




### -param Enlistment [in]

A pointer to an enlistment object. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.


### -param LastReference [out, optional]

A pointer to a BOOLEAN-typed variable. This variable receives <b>TRUE</b> if the reference count is zero after <b>TmDereferenceEnlistmentKey</b> decrements it. Otherwise, the variable receives <b>FALSE</b>.


## -returns



<b>TmDereferenceEnlistmentKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The reference count of the specified enlistment object is zero and cannot be decremented.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmreferenceenlistmentkey">TmReferenceEnlistmentKey</a> routine increments the reference count for an enlistment object's key, and the <b>TmDereferenceEnlistmentKey</b> routine decrements the count.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmreferenceenlistmentkey">TmReferenceEnlistmentKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>
 

 

