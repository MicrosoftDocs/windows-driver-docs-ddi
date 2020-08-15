---
UID: NF:wdm.NtPrepareComplete
title: NtPrepareComplete function (wdm.h)
description: The ZwPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data.
old-location: kernel\zwpreparecomplete.htm
tech.root: kernel
ms.assetid: c3d9362e-8a9d-47df-a407-389a9bd65e3b
ms.date: 04/30/2018
keywords: ["NtPrepareComplete function"]
ms.keywords: NtPrepareComplete, ZwPrepareComplete, ZwPrepareComplete routine [Kernel-Mode Driver Architecture], kernel.zwpreparecomplete, ktm_ref_2690208e-0252-4e3f-84c6-29750139da00.xml, wdm/NtPrepareComplete, wdm/ZwPrepareComplete
f1_keywords:
 - "wdm/ZwPrepareComplete"
 - "ZwPrepareComplete"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwPrepareComplete
- NtPrepareComplete
targetos: Windows
req.typenames: 
---

# NtPrepareComplete function


## -description


The <b>ZwPrepareComplete</b> routine notifies KTM that the calling resource manager has finished preparing a transaction's data.


## -parameters




### -param EnlistmentHandle 
[in]
A handle to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SUBORDINATE_RIGHTS access to the object.


### -param TmVirtualClock 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwPrepareComplete</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



A resource manager must call <b>ZwPrepareComplete</b> after it has finished servicing a TRANSACTION_NOTIFY_PREPARE <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-notifications">notification</a>.

After a resource manager has called <b>ZwPrepareComplete</b>, it cannot roll back the transaction.

For more information about <b>ZwPrepareComplete</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-commit-operations">Handling Commit Operations</a>.

<b>NtPrepareComplete</b> and <b>ZwPrepareComplete</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmpreparecomplete">TmPrepareComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepreparecomplete">ZwPrePrepareComplete</a>
 

 

