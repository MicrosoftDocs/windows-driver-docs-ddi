---
UID: NF:wdm.TmReadOnlyEnlistment
title: TmReadOnlyEnlistment function (wdm.h)
description: The TmReadOnlyEnlistment routine sets a specified enlistment to be read-only.
old-location: kernel\tmreadonlyenlistment.htm
tech.root: kernel
ms.assetid: 7d375152-c1d2-4e6d-a6a8-7394a7ef0e35
ms.date: 04/30/2018
keywords: ["TmReadOnlyEnlistment function"]
ms.keywords: TmReadOnlyEnlistment, TmReadOnlyEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmreadonlyenlistment, ktm_ref_fbd80117-d891-4e06-b271-5d838e7ecab0.xml, wdm/TmReadOnlyEnlistment
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
targetos: Windows
req.typenames: 
f1_keywords:
 - TmReadOnlyEnlistment
 - wdm/TmReadOnlyEnlistment
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
 - TmReadOnlyEnlistment
---

# TmReadOnlyEnlistment function


## -description

The <b>TmReadOnlyEnlistment</b> routine sets a specified enlistment to be read-only.

## -parameters

### -param Enlistment 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.

### -param TmVirtualClock 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>TmReadOnlyEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_NOT_REQUESTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state. For example, an enlistment cannot be read-only if the ENLISTMENT_SUPERIOR flag was specified to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>TmReadOnlyEnlistment</b> routine is a pointer-based version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntreadonlyenlistment">ZwReadOnlyEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntreadonlyenlistment">ZwReadOnlyEnlistment</a>

