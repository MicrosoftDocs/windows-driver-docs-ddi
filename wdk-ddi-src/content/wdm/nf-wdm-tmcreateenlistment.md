---
UID: NF:wdm.TmCreateEnlistment
title: TmCreateEnlistment function (wdm.h)
description: The TmCreateEnlistment routine creates a new enlistment object for a transaction.
old-location: kernel\tmcreateenlistment.htm
tech.root: kernel
ms.assetid: 84fcbc30-993c-430b-a8b9-aefca44e478e
ms.date: 04/30/2018
ms.keywords: TmCreateEnlistment, TmCreateEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmcreateenlistment, ktm_ref_79bc27ad-3c37-4396-9c9d-5bc429299db4.xml, wdm/TmCreateEnlistment
ms.topic: function
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
- TmCreateEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmCreateEnlistment function


## -description


The <b>TmCreateEnlistment</b> routine creates a new <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> for a transaction.


## -parameters




### -param EnlistmentHandle [out]

A pointer to a caller-allocated variable that receives a handle to the new enlistment object if the call to <b>TmCreateEnlistment</b> succeeds.


### -param PreviousMode [in]

The processor mode of the process that will use the enlistment handle to access the enlistment object. This value must be either <b>UserMode</b> or <b>KernelMode</b>.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the enlistment object. For more information about this parameter, see the description of the <i>DesiredAccess</i> parameter for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>.


### -param ObjectAttributes [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>. 


### -param ResourceManager [in]

A pointer to a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a> provided.


### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a> provided. KTM adds this transaction to the list of transactions that the calling resource manager is handling.


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

A bitwise OR of the TRANSACTION_NOTIFY_<i>XXX</i> values that are defined in Ktmtypes.h. This mask value specifies the types of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">transaction notifications</a> that KTM sends to the caller.


### -param EnlistmentKey [in, optional]

A pointer to caller-defined information that uniquely identifies the enlistment. The resource manager receives this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. The resource manager can maintain a reference count for this key by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564726">TmReferenceEnlistmentKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564671">TmDereferenceEnlistmentKey</a>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>TmCreateEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>CreateOptions</i> or <i>NotificationMask</i> parameter is invalid, or KTM could not find the transaction that the <i>Transaction</i> parameter specifies.

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
The enlistment failed because the transaction that the <i>Transaction</i> parameter specifies is not active.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_SUPERIOR_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The caller tried to register as a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> but a superior enlistment already exists.

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



The <b>TmCreateEnlistment</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>
 

 

