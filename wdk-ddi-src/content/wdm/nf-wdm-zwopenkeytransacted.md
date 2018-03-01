---
UID: NF:wdm.ZwOpenKeyTransacted
title: ZwOpenKeyTransacted function
author: windows-driver-content
description: The ZwOpenKeyTransacted routine opens an existing registry key and associates the key with a transaction.
old-location: kernel\zwopenkeytransacted.htm
old-project: kernel
ms.assetid: 9fd9aabd-3452-461d-b051-c3130b22ef5c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ZwOpenKeyTransacted, ZwOpenKeyTransacted routine [Kernel-Mode Driver Architecture], k111_e4192ee9-7dba-48d2-81be-38b33ff0b1d6.xml, kernel.zwopenkeytransacted, wdm/ZwOpenKeyTransacted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
-	ZwOpenKeyTransacted
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwOpenKeyTransacted function


## -description


The <b>ZwOpenKeyTransacted</b> routine opens an existing registry key and associates the key with a transaction. 


## -syntax


````
NTSTATUS ZwOpenKeyTransacted(
  _Out_ PHANDLE            KeyHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_  HANDLE             TransactionHandle
);
````


## -parameters




### -param KeyHandle [out]

A pointer to a HANDLE variable into which the routine writes the handle to the key. 


### -param DesiredAccess [in]

Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> routine. 


### -param ObjectAttributes [in]

A pointer to the object attributes of the key being opened. This parameter points to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this handle, you can call the <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> routine. Or, if you have a pointer to a transaction object, you can supply the pointer to the <a href="..\ntifs\nf-ntifs-obopenobjectbypointer.md">ObOpenObjectByPointer</a> routine to obtain the corresponding transaction handle. 


## -returns



<b>ZwOpenKeyTransacted</b> returns STATUS_SUCCESS if the call successfully opens the key. Possible error return values include the following:

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
The <i>ObjectAttributes</i> parameter is <b>NULL</b> or points to invalid information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The registry path in the object attributes is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry path in the object attributes was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required access rights to open a handle for the named registry key.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation operation failed.

</td>
</tr>
</table>
 




## -remarks



This routine provides a handle with which the caller can access a registry key. Additionally, this routine associates the key with an active transaction.

After the handle that is pointed to by <i>KeyHandle</i> is no longer being used, the driver must call the <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> routine to close it.

If the specified key does not exist in the registry, <b>ZwOpenKeyTransacted</b> returns an error status value and does not supply a key handle. Unlike the <a href="..\wdm\nf-wdm-zwcreatekeytransacted.md">ZwCreateKeyTransacted</a> routine, the <b>ZwOpenKeyTransacted</b> routine does not create the specified key if the key does not exist. Both <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransacted</b> associate a registry key with a transaction.

The <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a> routine is similar to <b>ZwOpenKeyTransacted</b>, but does not associate a key with a transaction.

After a kernel-mode driver obtains a handle to a transaction (for example, by calling <b>ZwCreateTransaction</b>), the driver can perform a series of registry operations that are part of this transaction. The driver can close the transaction either by committing to the changes that were made in the transaction or by rolling back the transaction.

After the driver successfully completes all registry operations that are part of a transaction, it can call the <a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a> routine to commit to the changes. The driver can call the <a href="..\wdm\nf-wdm-zwrollbacktransaction.md">ZwRollbackTransaction</a> routine to roll back the transaction.

During a transaction, a registry operation is part of the transaction if the system call that performs the operation meets either of the following conditions:

<ul>
<li>
The call specifies, as an input parameter, the transaction handle. For example, calls to <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransacted</b> can associate one or more keys with the transaction. 

</li>
<li>
The call specifies, as an input parameter, a registry key handle that was obtained by a call to <b>ZwCreateKeyTransacted</b> or <b>ZwOpenKeyTransacted</b> to which the transaction handle was supplied. For example, a call to the <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a> routine can use a key handle that was obtained in this way to set the value of a registry key as part of a transaction. 

</li>
</ul>
For more information about kernel-mode transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565408">Using Kernel Transaction Manager</a>.

<b>ZwOpenKeyTransacted</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about how to work with registry keys in kernel mode, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-zwopenkeytransactedex.md">ZwOpenKeyTransactedEx</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a>



<a href="..\wdm\nf-wdm-zwcreatekeytransacted.md">ZwCreateKeyTransacted</a>



<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>



<a href="..\ntifs\nf-ntifs-obopenobjectbypointer.md">ObOpenObjectByPointer</a>



<a href="..\wdm\nf-wdm-zwrollbacktransaction.md">ZwRollbackTransaction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenKeyTransacted routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

