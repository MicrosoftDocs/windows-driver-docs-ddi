---
UID: NF:wdm.NtSetInformationTransaction
title: NtSetInformationTransaction function (wdm.h)
description: The ZwSetInformationTransaction routine sets information for a specified transaction.
old-location: kernel\zwsetinformationtransaction.htm
tech.root: kernel
ms.assetid: 47e729d8-241e-47f0-a595-d95c5ac516a4
ms.date: 04/30/2018
ms.keywords: NtSetInformationTransaction, ZwSetInformationTransaction, ZwSetInformationTransaction routine [Kernel-Mode Driver Architecture], kernel.zwsetinformationtransaction, ktm_ref_575490bd-1003-43b3-8e41-676c4b0e4f25.xml, wdm/NtSetInformationTransaction, wdm/ZwSetInformationTransaction
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwSetInformationTransaction
- NtSetInformationTransaction
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtSetInformationTransaction function


## -description


The <b>ZwSetInformationTransaction</b> routine sets information for a specified transaction.


## -parameters




### -param TransactionHandle [in]

A handle to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-objects">transaction object</a> that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>. The handle must have TRANSACTION_SET_INFORMATION access to the object.


### -param TransactionInformationClass [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>-typed value that specifies the type of information to set. The value must be <b>TransactionPropertiesInformation</b>.


### -param TransactionInformation [in]

A pointer to a caller-allocated buffer that contains the information to set. The buffer's structure type must be <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>.


### -param TransactionInformationLength [in]

The length, in bytes, of the buffer that the <i>TransactionInformation</i> parameter points to.


## -returns



<b>ZwSetInformationTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The <i>TransactionInformationClass </i>parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The handle that the <i>TransactionHandle</i> parameter specifies is not a handle to a transaction object.

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
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>TransactionInformationLength </i>parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The contents of the buffer that the <i>TransactionInformation </i>buffer specifies is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



For more information about <b>ZwSetInformationTransaction</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-transactional-client">Creating a Transactional Client</a>.

<b>NtSetInformationTransaction</b> and <b>ZwSetInformationTransaction</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopentransaction">ZwOpenTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>
 

 

