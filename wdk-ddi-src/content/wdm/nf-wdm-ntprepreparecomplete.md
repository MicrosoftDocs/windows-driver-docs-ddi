---
UID: NF:wdm.NtPrePrepareComplete
title: NtPrePrepareComplete function (wdm.h)
description: The ZwPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data.
old-location: kernel\zwprepreparecomplete.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["NtPrePrepareComplete function"]
ms.keywords: NtPrePrepareComplete, ZwPrePrepareComplete, ZwPrePrepareComplete routine [Kernel-Mode Driver Architecture], kernel.zwprepreparecomplete, ktm_ref_f34acd5c-6983-4f8a-86ca-968dde152526.xml, wdm/NtPrePrepareComplete, wdm/ZwPrePrepareComplete
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
 - NtPrePrepareComplete
 - wdm/NtPrePrepareComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwPrePrepareComplete
 - NtPrePrepareComplete
---

# NtPrePrepareComplete function


## -description

The <b>ZwPrePrepareComplete</b> routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data.

## -parameters

### -param EnlistmentHandle 

[in]
A handle to an <a href="/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SUBORDINATE_RIGHTS access to the object.

### -param TmVirtualClock 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>ZwPrePrepareComplete</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not a handle to an enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The object handle is invalid.

</td>
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
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

A resource manager must call <b>ZwPrePrepareComplete</b> after it has finished servicing a TRANSACTION_NOTIFY_PREPREPARE <a href="/windows-hardware/drivers/kernel/transaction-notifications">notification</a>.

For more information about <b>ZwPrePrepareComplete</b>, see <a href="/windows-hardware/drivers/kernel/handling-commit-operations">Handling Commit Operations</a>.

<b>NtPrePrepareComplete</b> and <b>ZwPrePrepareComplete</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmprepreparecomplete">TmPrePrepareComplete</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreparecomplete">ZwPrepareComplete</a>
