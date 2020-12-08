---
UID: NF:wdm.NtQueryInformationTransaction
title: NtQueryInformationTransaction function (wdm.h)
description: The ZwQueryInformationTransaction routine retrieves information about a specified transaction.
old-location: kernel\zwqueryinformationtransaction.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["NtQueryInformationTransaction function"]
ms.keywords: NtQueryInformationTransaction, ZwQueryInformationTransaction, ZwQueryInformationTransaction routine [Kernel-Mode Driver Architecture], kernel.zwqueryinformationtransaction, ktm_ref_ffef2acc-e180-4adf-8aa5-31ee7dae0592.xml, wdm/NtQueryInformationTransaction, wdm/ZwQueryInformationTransaction
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
 - NtQueryInformationTransaction
 - wdm/NtQueryInformationTransaction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryInformationTransaction
 - NtQueryInformationTransaction
---

# NtQueryInformationTransaction function


## -description

The <b>ZwQueryInformationTransaction</b> routine retrieves information about a specified transaction.

## -parameters

### -param TransactionHandle 

[in]
A handle to a <a href="/windows-hardware/drivers/kernel/transaction-objects">transaction object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>. The handle must have TRANSACTION_QUERY_INFORMATION access to the object.

### -param TransactionInformationClass 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>-typed value that specifies the information to obtain. The value must be one of the following values:

<ul>
<li>
<b>TransactionBasicInformation</b>

</li>
<li>
<b>TransactionPropertiesInformation</b>

</li>
<li>
<b>TransactionEnlistmentInformation</b>

</li>
</ul>
The <b>TransactionFullInformation</b> value is not used with <b>ZwQueryInformationTransaction</b>.

### -param TransactionInformation 

[out]
A pointer to a caller-allocated buffer that receives the information that the <i>TransactionInformationClass</i> parameter specifies. The buffer's structure type must be <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>, or <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a>.

### -param TransactionInformationLength 

[in]
The length, in bytes, of the buffer that the <i>TransactionInformation</i> parameter points to, including the length of any additional array elements that the caller has allocated to receive information.

### -param ReturnLength 

[out, optional]
A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>TransactionInformation</i> buffer. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>ZwQueryInformationTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
The <i>TransactionInformationClass</i> parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The length of the buffer that is specified by the <i>TransactionInformationLength</i> parameter is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The handle that the <i>TransactionHandle </i>parameter specifies is not a handle to a transaction object.

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
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the transaction object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>TransactionInformation </i>parameter specifies is too small.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

For more information about how to use <b>ZwQueryInformationTransaction</b>, see <a href="/windows-hardware/drivers/kernel/creating-a-transactional-client">Creating a Transactional Client</a>.

<b>NtQueryInformationTransaction</b> and <b>ZwQueryInformationTransaction</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmgettransactionid">TmGetTransactionId</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a>
