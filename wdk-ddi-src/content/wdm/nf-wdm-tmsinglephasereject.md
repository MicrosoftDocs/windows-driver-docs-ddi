---
UID: NF:wdm.TmSinglePhaseReject
title: TmSinglePhaseReject function (wdm.h)
description: The TmSinglePhaseReject routine informs KTM that the calling resource manager will not support a single-phase commit operation for a specified enlistment.
old-location: kernel\tmsinglephasereject.htm
tech.root: kernel
ms.assetid: 8fc92d51-40be-439b-abee-54ad19a86a89
ms.date: 04/30/2018
keywords: ["TmSinglePhaseReject function"]
ms.keywords: TmSinglePhaseReject, TmSinglePhaseReject routine [Kernel-Mode Driver Architecture], kernel.tmsinglephasereject, ktm_ref_16802b39-057c-4d45-9da0-3f63f4589a44.xml, wdm/TmSinglePhaseReject
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
 - TmSinglePhaseReject
 - wdm/TmSinglePhaseReject
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
 - TmSinglePhaseReject
---

# TmSinglePhaseReject function


## -description

The <b>TmSinglePhaseReject</b> routine informs KTM that the calling resource manager will not support a <a href="/windows-hardware/drivers/kernel/handling-commit-operations">single-phase commit operation</a> for a specified enlistment.

## -parameters

### -param Enlistment 

[in]
A pointer to an <a href="/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.

### -param TmVirtualClock 

[in]
A pointer to a <a href="/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>TmSinglePhaseReject</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 

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
The transaction or its enlistment is not in the correct state.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>TmSinglePhaseReject</b> routine is a pointer-based version of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsinglephasereject">ZwSinglePhaseReject</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsinglephasereject">ZwSinglePhaseReject</a>