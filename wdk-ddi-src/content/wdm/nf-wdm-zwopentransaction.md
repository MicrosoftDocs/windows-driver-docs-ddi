---
UID: NF:wdm.ZwOpenTransaction
title: ZwOpenTransaction function (wdm.h)
description: The ZwOpenTransaction routine obtains a handle to an existing transaction object.
old-location: kernel\zwopentransaction.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwOpenTransaction function"]
ms.keywords: NtOpenTransaction, ZwOpenTransaction, ZwOpenTransaction routine [Kernel-Mode Driver Architecture], kernel.zwopentransaction, ktm_ref_ed0e1a06-e5e2-4328-aeeb-d56a78d6a757.xml, wdm/NtOpenTransaction, wdm/ZwOpenTransaction
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
 - ZwOpenTransaction
 - wdm/ZwOpenTransaction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenTransaction
 - NtOpenTransaction
---

# ZwOpenTransaction function


## -description

The <b>ZwOpenTransaction</b> routine obtains a handle to an existing <a href="/windows-hardware/drivers/kernel/transaction-objects">transaction object</a>.

## -parameters

### -param TransactionHandle 

[out]
A pointer to a caller-allocated variable that receives a handle to the transaction object if <b>ZwOpenTransaction</b> returns STATUS_SUCCESS.

### -param DesiredAccess 

[in]
An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction object. For information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>.

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. The <i>ObjectAttributes</i> parameter is optional and can be <b>NULL</b>.

### -param Uow 

[in]
A pointer to a GUID that is a transaction object's <a href="/windows-hardware/drivers/kernel/ktm-objects">unit of work (UOW) identifier</a>. This GUID identifies the transaction object to open.

### -param TmHandle 

[in, optional]
A handle to a <a href="/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>. If this parameter is not <b>NULL</b>, KTM searches only for transaction objects that belong to the specified transaction manager object. If this parameter is <b>NULL</b>, KTM searches all transaction objects.

## -returns

<b>ZwCreateTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The <i>DesiredAccess</i> or <i>Uow</i> parameter was zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not a handle to a transaction object.

</td>
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
<dt><b>STATUS_TRANSACTION_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
KTM could not find the transaction object.

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

Typically, a resource manager calls <b>ZwOpenTransaction</b> after it receives a transaction UOW from a transactional client that had previously called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>. 

For more information about <b>ZwOpenTransaction</b>, see <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>.

<b>NtOpenTransaction</b> and <b>ZwOpenTransaction</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcommittransaction">ZwCommitTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrollbacktransaction">ZwRollbackTransaction</a>
