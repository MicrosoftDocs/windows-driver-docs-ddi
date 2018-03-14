---
UID: NF:wdm.ZwRollbackTransaction
title: ZwRollbackTransaction function
author: windows-driver-content
description: The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction.
old-location: kernel\zwrollbacktransaction.htm
old-project: kernel
ms.assetid: 865349bd-400d-4acf-a2f7-33da128702be
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: NtRollbackTransaction, ZwRollbackTransaction, ZwRollbackTransaction routine [Kernel-Mode Driver Architecture], kernel.zwrollbacktransaction, ktm_ref_c29e1cd7-ffe0-4dab-be7f-a50a1d430ae3.xml, wdm/NtRollbackTransaction, wdm/ZwRollbackTransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwRollbackTransaction
-	NtRollbackTransaction
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwRollbackTransaction function


## -description


The <b>ZwRollbackTransaction</b> routine initiates a rollback operation for a specified transaction.


## -syntax


````
NTSTATUS ZwRollbackTransaction(
  _In_ HANDLE  TransactionHandle,
  _In_ BOOLEAN Wait
);
````


## -parameters




### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>. The handle must have TRANSACTION_ROLLBACK access to the object.


### -param Wait [in]

A Boolean value that the caller sets to <b>TRUE</b> for synchronous operation or <b>FALSE</b> for asynchronous operation. If this parameter is set to <b>TRUE</b>, the call does not return until the rollback operation is complete.


## -returns



<b>ZwRollbackTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
<dt><b>STATUS_TRANSACTION_ALREADY_COMMITTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction cannot be rolled back because it has already been committed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The transaction has not been committed but its current state does not permit rollback.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Rollback notifications have been queued to resource managers, and the caller specified <b>FALSE</b> for the <i>Wait</i> parameter.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



For more information about <b>ZwRollbackTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546928">Handling Rollback Operations</a>.

<b>NtRollbackEnlistment</b> and <b>ZwRollbackEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>



<a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>



<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>



 

 


