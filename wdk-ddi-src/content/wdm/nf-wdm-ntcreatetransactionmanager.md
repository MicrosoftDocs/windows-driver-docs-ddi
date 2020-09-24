---
UID: NF:wdm.NtCreateTransactionManager
title: NtCreateTransactionManager function (wdm.h)
description: The ZwCreateTransactionManager routine creates a new transaction manager object.
old-location: kernel\zwcreatetransactionmanager.htm
tech.root: kernel
ms.assetid: 9c9f0a8b-7add-4ab1-835d-39f508ce32a9
ms.date: 04/30/2018
keywords: ["NtCreateTransactionManager function"]
ms.keywords: NtCreateTransactionManager, ZwCreateTransactionManager, ZwCreateTransactionManager routine [Kernel-Mode Driver Architecture], kernel.zwcreatetransactionmanager, ktm_ref_56fad0b5-053d-4d65-bdb3-8c2d09fee541.xml, wdm/NtCreateTransactionManager, wdm/ZwCreateTransactionManager
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
 - NtCreateTransactionManager
 - wdm/NtCreateTransactionManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwCreateTransactionManager
 - NtCreateTransactionManager
---

# NtCreateTransactionManager function


## -description

The <b>ZwCreateTransactionManager</b> routine creates a new transaction manager object.

## -parameters

### -param TmHandle 

[out]
A pointer to a caller-allocated variable that receives a handle to the new <a href="/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>.

### -param DesiredAccess 

[in]
An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction manager object. In addition to the access rights that are defined for all kinds of objects (see <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>), the caller can specify any of the following access right flags for transaction manager objects. 

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Allows the caller to</th>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_CREATE_RM

</td>
<td>
Create a resource manager (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>).

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_QUERY_INFORMATION

</td>
<td>
Obtain information about the transaction manager (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntenumeratetransactionobject">ZwEnumerateTransactionObject</a>). Also required for <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>.) 

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_RECOVER

</td>
<td>
Recover the transaction manager (see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollforwardtransactionmanager">ZwRollforwardTransactionManager</a>).

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_RENAME

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_SET_INFORMATION

</td>
<td>
Not used.

</td>
</tr>
</table>
 

Alternatively, you can specify one or more of the following <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> bitmaps. These bitmaps combine the flags from the previous table with the STANDARD_RIGHTS_<i>XXX</i> flags that are described on the <b>ACCESS_MASK</b> reference page. You can also combine these bitmaps with additional flags from the preceding table. The following table shows how the bitmaps correspond to specific access rights.

<table>
<tr>
<th>Rights bitmap</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ and TRANSACTIONMANAGER_QUERY_INFORMATION

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, TRANSACTIONMANAGER_SET_INFORMATION, TRANSACTIONMANAGER_RECOVER, TRANSACTIONMANAGER_RENAME, and TRANSACTIONMANAGER_CREATE_RM

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_REQUIRED, TRANSACTIONMANAGER_GENERIC_READ, TRANSACTIONMANAGER_GENERIC_WRITE, and TRANSACTIONMANAGER_GENERIC_EXECUTE 

</td>
</tr>
</table>

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.

### -param LogFileName 

[in, optional]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path and file name of a <a href="/windows-hardware/drivers/kernel/using-log-streams-with-ktm">CLFS log file stream</a> to be associated with the transaction manager object. This parameter must be <b>NULL</b> if the <i>CreateOptions</i> parameter is TRANSACTION_MANAGER_VOLATILE. Otherwise, this parameter must be non-<b>NULL</b>. For more information, see the following Remarks section.

### -param CreateOptions 

[in, optional]
Optional object creation flags. The following table contains the available flags, which are defined in Ktmtypes.h.

<table>
<tr>
<th>Option flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_VOLATILE

</td>
<td>
The transaction manager object will be volatile. Therefore, it will not use a log file.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_DEFAULT

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_VOLUME

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_HIVES

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_LOWEST

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_RECOVERY

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_PROGRESS

</td>
<td>
For internal use only.

</td>
</tr>
</table>

### -param CommitStrength 

[in, optional]
Reserved for future use. This parameter must be zero.

## -returns

<b>ZwCreateTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The value of an input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
KTM could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_CORRUPTION_DETECTED</b></dt>
</dl>
</td>
<td width="60%">
KTM encountered an error while creating or opening the log file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>
</td>
<td width="60%">
A security descriptor contains an invalid access control list (ACL).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
A security descriptor contains an invalid security identifier (SID).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The object name that the <i>ObjectAttributes </i>parameter specifies already exists.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
The operating system detected a duplicate object name. The error might indicate that the log stream is already being used.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The object name that the <i>ObjectAttributes </i>parameter specifies is invalid.

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

If the log file stream that the <i>LogFileName </i>parameter specifies does not exist, KTM calls CLFS to create the stream. If the stream already exists, KTM calls CLFS to open the stream.

Your TPS component must call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a> after it has called <b>ZwCreateTransactionManager</b>

If your TPS component specifies the TRANSACTION_MANAGER_VOLATILE flag in the <i>CreateOptions </i>parameter, all resource managers that are associated with the transaction manager object must specify the RESOURCE_MANAGER_VOLATILE flag when they call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>.

A TPS component that calls <b>ZwCreateTransactionManager</b> must eventually call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close the object handle.

For more information about how use <b>ZwCreateTransactionManager</b>, see <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>.

<b>NtCreateTransactionManager</b> and <b>ZwCreateTransactionManager</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransactionmanager">ZwOpenTransactionManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollforwardtransactionmanager">ZwRollforwardTransactionManager</a>