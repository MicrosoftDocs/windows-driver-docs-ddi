---
UID: NF:wdm.ZwOpenKeyTransacted
title: ZwOpenKeyTransacted function (wdm.h)
description: The ZwOpenKeyTransacted routine opens an existing registry key and associates the key with a transaction.
old-location: kernel\zwopenkeytransacted.htm
tech.root: kernel
ms.assetid: 9fd9aabd-3452-461d-b051-c3130b22ef5c
ms.date: 04/30/2018
keywords: ["ZwOpenKeyTransacted function"]
ms.keywords: ZwOpenKeyTransacted, ZwOpenKeyTransacted routine [Kernel-Mode Driver Architecture], k111_e4192ee9-7dba-48d2-81be-38b33ff0b1d6.xml, kernel.zwopenkeytransacted, wdm/ZwOpenKeyTransacted
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwOpenKeyTransacted
 - wdm/ZwOpenKeyTransacted
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenKeyTransacted
---

# ZwOpenKeyTransacted function


## -description

The <b>ZwOpenKeyTransacted</b> routine opens an existing registry key and associates the key with a transaction.

## -parameters

### -param KeyHandle 

[out]
A pointer to a HANDLE variable into which the routine writes the handle to the key.

### -param DesiredAccess 

[in]
Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine.

### -param ObjectAttributes 

[in]
A pointer to the object attributes of the key being opened. This parameter points to an <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.

### -param TransactionHandle 

[in]
A handle to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-objects">transaction object</a>. To obtain this handle, you can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a> routine. Or, if you have a pointer to a transaction object, you can supply the pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-obopenobjectbypointer">ObOpenObjectByPointer</a> routine to obtain the corresponding transaction handle.

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

After the handle that is pointed to by <i>KeyHandle</i> is no longer being used, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> routine to close it.

If the specified key does not exist in the registry, <b>ZwOpenKeyTransacted</b> returns an error status value and does not supply a key handle. Unlike the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekeytransacted">ZwCreateKeyTransacted</a> routine, the <b>ZwOpenKeyTransacted</b> routine does not create the specified key if the key does not exist. Both <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransacted</b> associate a registry key with a transaction.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a> routine is similar to <b>ZwOpenKeyTransacted</b>, but does not associate a key with a transaction.

After a kernel-mode driver obtains a handle to a transaction (for example, by calling <b>ZwCreateTransaction</b>), the driver can perform a series of registry operations that are part of this transaction. The driver can close the transaction either by committing to the changes that were made in the transaction or by rolling back the transaction.

After the driver successfully completes all registry operations that are part of a transaction, it can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommittransaction">ZwCommitTransaction</a> routine to commit to the changes. The driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbacktransaction">ZwRollbackTransaction</a> routine to roll back the transaction.

During a transaction, a registry operation is part of the transaction if the system call that performs the operation meets either of the following conditions:

<ul>
<li>
The call specifies, as an input parameter, the transaction handle. For example, calls to <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransacted</b> can associate one or more keys with the transaction. 

</li>
<li>
The call specifies, as an input parameter, a registry key handle that was obtained by a call to <b>ZwCreateKeyTransacted</b> or <b>ZwOpenKeyTransacted</b> to which the transaction handle was supplied. For example, a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a> routine can use a key handle that was obtained in this way to set the value of a registry key as part of a transaction. 

</li>
</ul>
For more information about kernel-mode transactions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-kernel-transaction-manager">Using Kernel Transaction Manager</a>.

<b>ZwOpenKeyTransacted</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>.

For more information about how to work with registry keys in kernel mode, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-obopenobjectbypointer">ObOpenObjectByPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommittransaction">ZwCommitTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekeytransacted">ZwCreateKeyTransacted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkeytransactedex">ZwOpenKeyTransactedEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbacktransaction">ZwRollbackTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>

