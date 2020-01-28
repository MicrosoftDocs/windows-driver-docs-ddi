---
UID: NF:wdm.TmPrepareEnlistment
title: TmPrepareEnlistment function (wdm.h)
description: The TmPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction.
old-location: kernel\tmprepareenlistment.htm
tech.root: kernel
ms.assetid: 9bd0dd4a-be27-4398-9bbd-129955ce310f
ms.date: 04/30/2018
ms.keywords: TmPrepareEnlistment, TmPrepareEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmprepareenlistment, ktm_ref_c5ed06cd-98cc-4e0c-9311-07dcaea060fa.xml, wdm/TmPrepareEnlistment
f1_keywords:
 - "wdm/TmPrepareEnlistment"
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
- TmPrepareEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmPrepareEnlistment function


## -description


The <b>TmPrepareEnlistment</b> routine initiates the prepare operation for a specified enlistment's transaction.


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>TmPrepareEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_SUPERIOR</b></dt>
</dl>
</td>
<td width="60%">
The caller is not a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> for the enlistment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_RESPONSE_NOT_ENLISTED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not register to receive TRANSACTION_NOTIFY_PREPARE_COMPLETE notifications.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The enlistment's transaction is not in a state that allows it to enter the prepare phase.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the enlistment object.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The <b>TmPrepareEnlistment</b> routine is a pointer-based version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepareenlistment">ZwPrepareEnlistment</a> routine.

Only superior transaction managers can call <b>TmPrepareEnlistment</b>.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepareenlistment">ZwPrepareEnlistment</a>
 

 

