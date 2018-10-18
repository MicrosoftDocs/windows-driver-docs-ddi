---
UID: NF:wdm.NtCreateEnlistment
title: NtCreateEnlistment function
author: windows-driver-content
description: The ZwCreateEnlistment routine creates a new enlistment object for a transaction.
old-location: kernel\zwcreateenlistment.htm
tech.root: kernel
ms.assetid: 5ffd8262-10b3-4c40-bd3e-050271338508
ms.date: 4/30/2018
ms.keywords: NtCreateEnlistment, ZwCreateEnlistment, ZwCreateEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwcreateenlistment, ktm_ref_30b47803-67b7-4a88-9f87-0dbee055f580.xml, wdm/NtCreateEnlistment, wdm/ZwCreateEnlistment
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwCreateEnlistment
-	NtCreateEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtCreateEnlistment function


## -description


The <b>ZwCreateEnlistment</b> routine creates a new <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> for a transaction.


## -parameters




### -param EnlistmentHandle [out]

A pointer to a caller-allocated variable that receives a handle to the new enlistment object if the call to <b>ZwCreateEnlistment</b> succeeds.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the enlistment object. In addition to the access rights that are defined for all kinds of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify any of the following access right flags for enlistment objects:

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
Query information about the enlistment (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567051">ZwQueryInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SET_INFORMATION

</td>
<td>
Set information for the enlistment (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567094">ZwSetInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_RECOVER

</td>
<td>
Recover the enlistment (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567075">ZwRecoverEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUBORDINATE_RIGHTS

</td>
<td>
Perform operations that a resource manager that is not superior performs (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567083">ZwRollbackEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567040">ZwPrePrepareComplete</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567037">ZwPrepareComplete</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff566418">ZwCommitComplete</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567081">ZwRollbackComplete</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567113">ZwSinglePhaseReject</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567074">ZwReadOnlyEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUPERIOR_RIGHTS

</td>
<td>
Perform operations that a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> must perform (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567039">ZwPrepareEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567044">ZwPrePrepareEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff566419">ZwCommitEnlistment</a>). 

</td>
</tr>
</table>
 

Alternatively, you can specify one or more of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmaps. These bitmaps combine the flags from the previous table with the STANDARD_RIGHTS_<i>XXX</i> flags that are described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> reference page. You can also combine these bitmaps together with additional flags from the previous table. The following table shows how the bitmaps correspond to specific access rights. 

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
 


### -param ResourceManagerHandle [in]

A handle to the caller's <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a> that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>.


### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>. KTM adds this transaction to the list of transactions that the calling resource manager is handling.


### -param ObjectAttributes [in, optional]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>. 


### -param CreateOptions [in, optional]

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
The caller is enlisting as a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> for the specified transaction.

</td>
</tr>
</table>
 

This parameter is optional and can be zero. 


### -param NotificationMask [in]

A bitwise OR of TRANSACTION_NOTIFY_<i>XXX</i> values that are defined in Ktmtypes.h. This mask specifies the types of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">transaction notifications</a> that KTM sends to the caller.


### -param EnlistmentKey [in, optional]

A pointer to caller-defined information that uniquely identifies the enlistment. The resource manager receives this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. The resource manager can maintain a reference count for this key by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564726">TmReferenceEnlistmentKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564671">TmDereferenceEnlistmentKey</a>. This parameter is optional and can be <b>NULL</b>. 


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
The caller tried to register as a superior transaction manager but a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> already exists.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>
</td>
<td width="60%">
The caller is trying to register as a superior transaction manager, but the caller's resource manager object is <a href="https://msdn.microsoft.com/b2841d56-650a-487c-a002-2521cd1b461b">volatile</a> while the associated transaction manager object is not volatile.

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
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A resource manager calls <b>ZwCreateEnlistment</b> to enlist in a transaction. 

Resource managers that are not superior must include the ENLISTMENT_SUBORDINATE_RIGHTS flag in their access mask. 


<a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">Superior transaction managers</a> must include the ENLISTMENT_SUPERIOR_RIGHTS flag in their access masks. Typically, a superior transaction manager includes code that calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567083">ZwRollbackEnlistment</a>, so it must also include the ENLISTMENT_SUBORDINATE_RIGHTS flag.

A resource manager that calls <b>ZwCreateEnlistment</b> must eventually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close the object handle.

Your resource manager can use the <i>EnlistmentKey</i> parameter to assign a unique value to each enlistment, such as a pointer to a data structure that contains information about the enlistment. For example, if the resource manager stores the enlistment object's handle in the structure, the resource manager can do the following:

<ol>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a> to obtain a notification.

</li>
<li>
Obtain the enlistment key value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a> structure.

</li>
<li>
Use the enlistment key to find the stored enlistment object handle.

</li>
<li>
Call routines that require the enlistment handle as input, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff566418">ZwCommitComplete</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567081">ZwRollbackComplete</a>.

</li>
</ol>
For more information about <b>ZwCreateEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542870">Creating a Superior Transaction Manager</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566418">ZwCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566419">ZwCommitEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567040">ZwPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567044">ZwPrePrepareEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567037">ZwPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567039">ZwPrepareEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567051">ZwQueryInformationEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567074">ZwReadOnlyEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567075">ZwRecoverEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567081">ZwRollbackComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567083">ZwRollbackEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567094">ZwSetInformationEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567113">ZwSinglePhaseReject</a>
 

 

