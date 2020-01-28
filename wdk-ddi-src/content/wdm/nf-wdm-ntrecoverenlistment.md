---
UID: NF:wdm.NtRecoverEnlistment
title: NtRecoverEnlistment function (wdm.h)
description: The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment.
old-location: kernel\zwrecoverenlistment.htm
tech.root: kernel
ms.assetid: 0f34d2d1-bb3a-4529-9ced-d9bed998c4ce
ms.date: 04/30/2018
ms.keywords: NtRecoverEnlistment, ZwRecoverEnlistment, ZwRecoverEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwrecoverenlistment, ktm_ref_0a6564fb-c6d1-4b4b-a278-a1d78395c1b4.xml, wdm/NtRecoverEnlistment, wdm/ZwRecoverEnlistment
f1_keywords:
 - "wdm/ZwRecoverEnlistment"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- ZwRecoverEnlistment
- NtRecoverEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtRecoverEnlistment function


## -description


The <b>ZwRecoverEnlistment</b> routine initiates a recovery operation for the transaction that is associated with a specified enlistment.


## -parameters




### -param EnlistmentHandle [in]

A handle to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_RECOVER access to the object.


### -param EnlistmentKey [in, optional]

A pointer to the enlistment key value that the resource manager previously specified as the <i>EnlistmentKey</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>. This parameter is optional and can be <b>NULL</b> if the resource manager did not provide an enlistment key when it called <b>ZwCreateEnlistment</b>. 


## -returns



<b>ZwRecoverEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
KTM has added a commit, rollback, or in-doubt notification to the resource manager's notification queue, and the resource manager is not using a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine.

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



After a resource manager calls <b>ZwRecoverEnlistment</b>, KTM delivers either a TRANSACTION_NOTIFY_COMMIT, TRANSACTION_NOTIFY_ROLLBACK, or TRANSACTION_NOTIFY_INDOUBT <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-notifications">notification</a> for the enlistment. Therefore, unless the resource manager is using a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine, it must immediately call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a> if <b>ZwRecoverEnlistment</b> returns STATUS_SUCCESS or STATUS_PENDING. 

For more information about <b>ZwRecoverEnlistment</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-recovery-operations">Handling Recovery Operations</a>.

<b>NtRecoverEnlistment</b> and <b>ZwRecoverEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmrecoverenlistment">TmRecoverEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>
 

 

