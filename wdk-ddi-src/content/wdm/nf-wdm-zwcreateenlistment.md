---
UID: NF:wdm.ZwCreateEnlistment
title: ZwCreateEnlistment function (wdm.h)
description: The ZwCreateEnlistment routine creates a new enlistment object for a transaction.
old-location: kernel\zwcreateenlistment.htm
tech.root: kernel
ms.assetid: 5ffd8262-10b3-4c40-bd3e-050271338508
ms.date: 04/30/2018
keywords: ["ZwCreateEnlistment function"]
ms.keywords: NtCreateEnlistment, ZwCreateEnlistment, ZwCreateEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwcreateenlistment, ktm_ref_30b47803-67b7-4a88-9f87-0dbee055f580.xml, wdm/NtCreateEnlistment, wdm/ZwCreateEnlistment
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwCreateEnlistment
 - wdm/ZwCreateEnlistment
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwCreateEnlistment
 - NtCreateEnlistment
---

# ZwCreateEnlistment function


## -description

The <b>ZwCreateEnlistment</b> routine creates a new <a href="/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> for a transaction.

## -parameters

### -param EnlistmentHandle 

[out]
A pointer to a caller-allocated variable that receives a handle to the new enlistment object if the call to <b>ZwCreateEnlistment</b> succeeds.

### -param DesiredAccess 

[in]
An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the caller's requested access to the enlistment object. In addition to the access rights that are defined for all kinds of objects (see <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>), the caller can specify any of the following access right flags for enlistment objects:

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Allows the caller to</th>
</tr>
<tr>
<td>
ENLISTMENT_QUERY_INFORMATION

</td>
<td>
Query information about the enlistment (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SET_INFORMATION

</td>
<td>
Set information for the enlistment (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_RECOVER

</td>
<td>
Recover the enlistment (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecoverenlistment">ZwRecoverEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUBORDINATE_RIGHTS

</td>
<td>
Perform operations that a resource manager that is not superior performs (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackenlistment">ZwRollbackEnlistment</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepreparecomplete">ZwPrePrepareComplete</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreparecomplete">ZwPrepareComplete</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitcomplete">ZwCommitComplete</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackcomplete">ZwRollbackComplete</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsinglephasereject">ZwSinglePhaseReject</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntreadonlyenlistment">ZwReadOnlyEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUPERIOR_RIGHTS

</td>
<td>
Perform operations that a <a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> must perform (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepareenlistment">ZwPrepareEnlistment</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreprepareenlistment">ZwPrePrepareEnlistment</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitenlistment">ZwCommitEnlistment</a>). 

</td>
</tr>
</table>
 

Alternatively, you can specify one or more of the following <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> bitmaps. These bitmaps combine the flags from the previous table with the STANDARD_RIGHTS_<i>XXX</i> flags that are described on the <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> reference page. You can also combine these bitmaps together with additional flags from the previous table. The following table shows how the bitmaps correspond to specific access rights. 

<table>
<tr>
<th>Generic access right</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
ENLISTMENT_GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ and ENLISTMENT_QUERY_INFORMATION

</td>
</tr>
<tr>
<td>
ENLISTMENT_GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, ENLISTMENT_SET_INFORMATION, ENLISTMENT_RECOVER, ENLISTMENT_REFERENCE, ENLISTMENT_SUBORDINATE_RIGHTS, and ENLISTMENT_SUPERIOR_RIGHTS

</td>
</tr>
<tr>
<td>
ENLISTMENT_GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, ENLISTMENT_RECOVER, ENLISTMENT_SUBORDINATE_RIGHTS, and ENLISTMENT_SUPERIOR_RIGHTS

</td>
</tr>
<tr>
<td>
ENLISTMENT_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_REQUIRED, ENLISTMENT_GENERIC_READ, ENLISTMENT_GENERIC_WRITE, and ENLISTMENT_GENERIC_EXECUTE

</td>
</tr>
</table>

### -param ResourceManagerHandle 

[in]
A handle to the caller's <a href="/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>.

### -param TransactionHandle 

[in]
A handle to a <a href="/windows-hardware/drivers/kernel/transaction-objects">transaction object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>. KTM adds this transaction to the list of transactions that the calling resource manager is handling.

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.

### -param CreateOptions 

[in, optional]
Enlistment option flags. The following table contains the only available flag. 

<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ENLISTMENT_SUPERIOR

</td>
<td>
The caller is enlisting as a <a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> for the specified transaction.

</td>
</tr>
</table>
 

This parameter is optional and can be zero.

### -param NotificationMask 

[in]
A bitwise OR of TRANSACTION_NOTIFY_<i>XXX</i> values that are defined in Ktmtypes.h. This mask specifies the types of <a href="/windows-hardware/drivers/kernel/transaction-notifications">transaction notifications</a> that KTM sends to the caller.

### -param EnlistmentKey 

[in, optional]
A pointer to caller-defined information that uniquely identifies the enlistment. The resource manager receives this pointer when it calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. The resource manager can maintain a reference count for this key by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmreferenceenlistmentkey">TmReferenceEnlistmentKey</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmdereferenceenlistmentkey">TmDereferenceEnlistmentKey</a>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>ZwCreateEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
An object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>CreateOptions</i> or <i>NotificationMask</i> parameter's value is invalid, or KTM could not find the transaction that the <i>TransactionHandle</i> parameter specifies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>
</td>
<td width="60%">
The enlistment failed because KTM or the resource manager is not in an operational state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_NOT_ACTIVE</b></dt>
</dl>
</td>
<td width="60%">
The enlistment failed because the transaction that the <i>TransactionHandle</i> parameter specifies is not active.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_SUPERIOR_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The caller tried to register as a superior transaction manager but a <a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> already exists.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>
</td>
<td width="60%">
The caller is trying to register as a superior transaction manager, but the caller's resource manager object is <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">volatile</a> while the associated transaction manager object is not volatile.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>DesiredAccess</i> parameter is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

A resource manager calls <b>ZwCreateEnlistment</b> to enlist in a transaction. 

Resource managers that are not superior must include the ENLISTMENT_SUBORDINATE_RIGHTS flag in their access mask. 


<a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">Superior transaction managers</a> must include the ENLISTMENT_SUPERIOR_RIGHTS flag in their access masks. Typically, a superior transaction manager includes code that calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackenlistment">ZwRollbackEnlistment</a>, so it must also include the ENLISTMENT_SUBORDINATE_RIGHTS flag.

A resource manager that calls <b>ZwCreateEnlistment</b> must eventually call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close the object handle.

Your resource manager can use the <i>EnlistmentKey</i> parameter to assign a unique value to each enlistment, such as a pointer to a data structure that contains information about the enlistment. For example, if the resource manager stores the enlistment object's handle in the structure, the resource manager can do the following:

<ol>
<li>
Call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a> to obtain a notification.

</li>
<li>
Obtain the enlistment key value from the <a href="/previous-versions/windows/hardware/drivers/ff564813(v=vs.85)">TRANSACTION_NOTIFICATION</a> structure.

</li>
<li>
Use the enlistment key to find the stored enlistment object handle.

</li>
<li>
Call routines that require the enlistment handle as input, such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitcomplete">ZwCommitComplete</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackcomplete">ZwRollbackComplete</a>.

</li>
</ol>
For more information about <b>ZwCreateEnlistment</b>, see <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a> and <a href="/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">Creating a Superior Transaction Manager</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a>



<a href="/previous-versions/windows/hardware/drivers/ff564813(v=vs.85)">TRANSACTION_NOTIFICATION</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitcomplete">ZwCommitComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommitenlistment">ZwCommitEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntgetnotificationresourcemanager">ZwGetNotificationResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepreparecomplete">ZwPrePrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreprepareenlistment">ZwPrePrepareEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpreparecomplete">ZwPrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntprepareenlistment">ZwPrepareEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntreadonlyenlistment">ZwReadOnlyEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecoverenlistment">ZwRecoverEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackcomplete">ZwRollbackComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbackenlistment">ZwRollbackEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsinglephasereject">ZwSinglePhaseReject</a>