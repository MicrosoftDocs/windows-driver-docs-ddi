---
UID: NF:wdm.TmRequestOutcomeEnlistment
title: TmRequestOutcomeEnlistment function (wdm.h)
description: The TmRequestOutcomeEnlistment routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.
old-location: kernel\tmrequestoutcomeenlistment.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["TmRequestOutcomeEnlistment function"]
ms.keywords: TmRequestOutcomeEnlistment, TmRequestOutcomeEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmrequestoutcomeenlistment, ktm_ref_9be6bea7-eae4-4621-8155-f8a06285bb97.xml, wdm/TmRequestOutcomeEnlistment
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
 - TmRequestOutcomeEnlistment
 - wdm/TmRequestOutcomeEnlistment
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
 - TmRequestOutcomeEnlistment
---

# TmRequestOutcomeEnlistment function


## -description

The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.

## -parameters

### -param Enlistment 

[in]
A pointer to an <a href="/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.

### -param TmVirtualClock 

[in]
A pointer to a <a href="/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>TmRequestOutcomeEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The specified enlistment is a <a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior enlistment</a>.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (result) for the transaction. A resource manager can call <b>TmRequestOutcomeEnlistment</b> after it has called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmpreparecomplete">TmPrepareComplete</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreparecomplete">ZwPrepareComplete</a>, if it later discovers that it cannot wait for an outcome because, for example, a surprise-removal of the disk has occurred. KTM might be able to force a rollback if all resource managers have not finished their prepare operations.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of Zw<i>Xxx</i> routines, see <a href="/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.

For more information about <b>TmCreateEnlistment</b>, see <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmpreparecomplete">TmPrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreparecomplete">ZwPrepareComplete</a>
