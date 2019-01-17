---
UID: NF:wdm.ZwOpenKeyTransactedEx
title: ZwOpenKeyTransactedEx function
description: The ZwOpenKeyTransactedEx routine opens an existing registry key and associates the key with a transaction.
old-location: kernel\zwopenkeytransactedex.htm
tech.root: kernel
ms.assetid: 8e3db1b4-6ee1-40a1-9818-434152fdffd7
ms.date: 04/30/2018
ms.keywords: ZwOpenKeyTransactedEx, ZwOpenKeyTransactedEx routine [Kernel-Mode Driver Architecture], k111_765ab476-0a2a-4eb4-ba87-387fa49ae118.xml, kernel.zwopenkeytransactedex, wdm/ZwOpenKeyTransactedEx
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
-	ZwOpenKeyTransactedEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenKeyTransactedEx function


## -description


The <b>ZwOpenKeyTransactedEx</b> routine opens an existing registry key and associates the key with a transaction. 


## -parameters




### -param KeyHandle [out]

A pointer to a HANDLE variable into which the routine writes the handle to the key. 


### -param DesiredAccess [in]

Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> routine. 


### -param ObjectAttributes [in]

A pointer to the object attributes of the key being opened. This parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param OpenOptions [in]

Specifies the options to apply when opening the key. Set this parameter to zero or to the bitwise OR of one or more of the following REG_OPTION_<i>XXX</i> flag bits.

<table>
<tr>
<th><i>OpenOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_OPEN_LINK

</td>
<td>
The key is a symbolic link. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE

</td>
<td>
The key should be opened with special privileges that allow backup and restore operations. This flag is not used by device and intermediate drivers.

</td>
</tr>
</table>
 


### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this handle, you can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> routine. Or, if you have a pointer to a transaction object, you can supply the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550985">ObOpenObjectByPointer</a> routine to obtain the corresponding transaction handle. 


## -returns



<b>ZwOpenKeyTransactedEx</b> returns STATUS_SUCCESS if the call successfully opens the key. Possible error return values include the following:

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
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The <i>OpenOptions</i> parameter value specifies invalid options.

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

After the handle that is pointed to by <i>KeyHandle</i> is no longer being used, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> routine to close it.

If the specified key does not exist in the registry, <b>ZwOpenKeyTransactedEx</b> returns an error status value and does not supply a key handle. Unlike the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566426">ZwCreateKeyTransacted</a> routine, the <b>ZwOpenKeyTransactedEx</b> routine does not create the specified key if the key does not exist. Both <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransactedEx</b> associate a registry key with a transaction.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567015">ZwOpenKeyEx</a> routine is similar to <b>ZwOpenKeyTransactedEx</b>, but does not associate a key with a transaction.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567018">ZwOpenKeyTransacted</a> routine is similar to <b>ZwOpenKeyTransactedEx</b> but does not accept an <i>OpenOptions</i> parameter. The <i>OpenOptions</i> parameter of <b>ZwOpenKeyTransactedEx</b> enables the caller to open a key that is a symbolic link, or to open a key for backup and restore operations. A call to <b>ZwOpenKeyTransactedEx</b> with <i>OpenOptions</i> parameter set to zero is equivalent to a call to <b>ZwOpenKeyTransacted</b>.

After a kernel-mode driver obtains a handle to a transaction (for example, by calling <b>ZwCreateTransaction</b>), the driver can perform a series of registry operations that are part of this transaction. The driver can close the transaction either by committing to the changes that were made in the transaction or by rolling back the transaction.

After the driver successfully completes all registry operations that are part of a transaction, it can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566420">ZwCommitTransaction</a> routine to commit to the changes. The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567086">ZwRollbackTransaction</a> routine to roll back the transaction.

During a transaction, a registry operation is part of the transaction if the system call that performs the operation meets either of the following conditions:

<ul>
<li>
The call specifies, as an input parameter, the transaction handle. For example, calls to <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransactedEx</b> can associate one or more keys with the transaction. 

</li>
<li>
The call specifies, as an input parameter, a registry key handle that was obtained by a call to <b>ZwCreateKeyTransacted</b> or <b>ZwOpenKeyTransactedEx</b> to which the transaction handle was supplied. For example, a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567109">ZwSetValueKey</a> routine can use a key handle that was obtained in this way to set the value of a registry key as part of a transaction. 

</li>
</ul>
For more information about kernel-mode transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565408">Using Kernel Transaction Manager</a>.

<b>ZwOpenKeyTransactedEx</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about how to work with registry keys in kernel mode, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550985">ObOpenObjectByPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566420">ZwCommitTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566426">ZwCreateKeyTransacted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567015">ZwOpenKeyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567018">ZwOpenKeyTransacted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567086">ZwRollbackTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567109">ZwSetValueKey</a>
 

 

