---
UID: NF:wdm.TmCommitComplete
title: TmCommitComplete function (wdm.h)
description: The TmCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction.
old-location: kernel\tmcommitcomplete.htm
tech.root: kernel
ms.assetid: a5f55966-98d9-42ec-9af6-254d2cb9a5bd
ms.date: 04/30/2018
keywords: ["TmCommitComplete function"]
ms.keywords: TmCommitComplete, TmCommitComplete routine [Kernel-Mode Driver Architecture], kernel.tmcommitcomplete, ktm_ref_e6357c60-303b-4d42-a0a2-1ff3766acbb9.xml, wdm/TmCommitComplete
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
 - TmCommitComplete
 - wdm/TmCommitComplete
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
 - TmCommitComplete
---

# TmCommitComplete function


## -description

The <b>TmCommitComplete</b> routine notifies KTM that the calling  resource manager has finished committing a transaction.

## -parameters

### -param Enlistment 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.

### -param TmVirtualClock 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>TmCommitComplete</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>TmCommitComplete</b> routine is a pointer-based version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitcomplete">ZwCommitComplete</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitcomplete">ZwCommitComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>

