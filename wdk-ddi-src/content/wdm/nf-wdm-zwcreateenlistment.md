---
UID: NF:wdm.ZwCreateEnlistment
title: ZwCreateEnlistment function
author: windows-driver-content
description: The ZwCreateEnlistment routine creates a new enlistment object for a transaction.
old-location: kernel\zwcreateenlistment.htm
old-project: kernel
ms.assetid: 5ffd8262-10b3-4c40-bd3e-050271338508
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwCreateEnlistment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwCreateEnlistment,NtCreateEnlistment
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwCreateEnlistment function



## -description
The <b>ZwCreateEnlistment</b> routine creates a new <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> for a transaction.



## -syntax

````
NTSTATUS ZwCreateEnlistment(
  _Out_    PHANDLE            EnlistmentHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     HANDLE             ResourceManagerHandle,
  _In_     HANDLE             TransactionHandle,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ ULONG              CreateOptions,
  _In_     NOTIFICATION_MASK  NotificationMask,
  _In_opt_ PVOID              EnlistmentKey
);
````


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
Query information about the enlistment (see <a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SET_INFORMATION

</td>
<td>
Set information for the enlistment (see <a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_RECOVER

</td>
<td>
Recover the enlistment (see <a href="..\wdm\nf-wdm-zwrecoverenlistment.md">ZwRecoverEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUBORDINATE_RIGHTS

</td>
<td>
Perform operations that a resource manager that is not superior performs (see <a href="..\wdm\nf-wdm-zwrollbackenlistment.md">ZwRollbackEnlistment</a>, <a href="..\wdm\nf-wdm-zwprepreparecomplete.md">ZwPrePrepareComplete</a>, <a href="..\wdm\nf-wdm-zwpreparecomplete.md">ZwPrepareComplete</a>, <a href="..\wdm\nf-wdm-zwcommitcomplete.md">ZwCommitComplete</a>, <a href="..\wdm\nf-wdm-zwrollbackcomplete.md">ZwRollbackComplete</a>, <a href="..\wdm\nf-wdm-zwsinglephasereject.md">ZwSinglePhaseReject</a>, <a href="..\wdm\nf-wdm-zwreadonlyenlistment.md">ZwReadOnlyEnlistment</a>). 

</td>
</tr>
<tr>
<td>
ENLISTMENT_SUPERIOR_RIGHTS

</td>
<td>
Perform operations that a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> must perform (see <a href="..\wdm\nf-wdm-zwprepareenlistment.md">ZwPrepareEnlistment</a>, <a href="..\wdm\nf-wdm-zwpreprepareenlistment.md">ZwPrePrepareEnlistment</a>, <a href="..\wdm\nf-wdm-zwcommitenlistment.md">ZwCommitEnlistment</a>). 

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

A handle to the caller's <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a> or <a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>.


### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>. KTM adds this transaction to the list of transactions that the calling resource manager is handling.


### -param ObjectAttributes [in, optional]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>. 


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

A pointer to caller-defined information that uniquely identifies the enlistment. The resource manager receives this pointer when it calls <a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. The resource manager can maintain a reference count for this key by calling <a href="..\wdm\nf-wdm-tmreferenceenlistmentkey.md">TmReferenceEnlistmentKey</a> and <a href="..\wdm\nf-wdm-tmdereferenceenlistmentkey.md">TmDereferenceEnlistmentKey</a>. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>ZwCreateEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>CreateOptions</i> or <i>NotificationMask</i> parameter's value is invalid, or KTM could not find the transaction that the <i>TransactionHandle</i> parameter specifies.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory allocation failed.
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>The enlistment failed because KTM or the resource manager is not in an operational state.
<dl>
<dt><b>STATUS_TRANSACTION_NOT_ACTIVE</b></dt>
</dl>The enlistment failed because the transaction that the <i>TransactionHandle</i> parameter specifies is not active.
<dl>
<dt><b>STATUS_TRANSACTION_SUPERIOR_EXISTS</b></dt>
</dl>The caller tried to register as a superior transaction manager but a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> already exists.
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>The caller is trying to register as a superior transaction manager, but the caller's resource manager object is <a href="kernel.creating_a_resource_manager#kernel.creating_a_volatile_resource_manager#kernel.creating_a_volatile_resource_manager">volatile</a> while the associated transaction manager object is not volatile.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The value of the <i>DesiredAccess</i> parameter is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
A resource manager calls <b>ZwCreateEnlistment</b> to enlist in a transaction. 

Resource managers that are not superior must include the ENLISTMENT_SUBORDINATE_RIGHTS flag in their access mask. 


<a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">Superior transaction managers</a> must include the ENLISTMENT_SUPERIOR_RIGHTS flag in their access masks. Typically, a superior transaction manager includes code that calls <a href="..\wdm\nf-wdm-zwrollbackenlistment.md">ZwRollbackEnlistment</a>, so it must also include the ENLISTMENT_SUBORDINATE_RIGHTS flag.

A resource manager that calls <b>ZwCreateEnlistment</b> must eventually call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close the object handle.

Your resource manager can use the <i>EnlistmentKey</i> parameter to assign a unique value to each enlistment, such as a pointer to a data structure that contains information about the enlistment. For example, if the resource manager stores the enlistment object's handle in the structure, the resource manager can do the following:

Call <a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a> to obtain a notification.

Obtain the enlistment key value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a> structure.

Use the enlistment key to find the stored enlistment object handle.

Call routines that require the enlistment handle as input, such as <a href="..\wdm\nf-wdm-zwcommitcomplete.md">ZwCommitComplete</a> or <a href="..\wdm\nf-wdm-zwrollbackcomplete.md">ZwRollbackComplete</a>.

For more information about <b>ZwCreateEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542870">Creating a Superior Transaction Manager</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcommitcomplete.md">ZwCommitComplete</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcommitenlistment.md">ZwCommitEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwpreparecomplete.md">ZwPrepareComplete</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwprepareenlistment.md">ZwPrepareEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwprepreparecomplete.md">ZwPrePrepareComplete</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwpreprepareenlistment.md">ZwPrePrepareEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwreadonlyenlistment.md">ZwReadOnlyEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwrecoverenlistment.md">ZwRecoverEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwrollbackcomplete.md">ZwRollbackComplete</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwrollbackenlistment.md">ZwRollbackEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsinglephasereject.md">ZwSinglePhaseReject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

