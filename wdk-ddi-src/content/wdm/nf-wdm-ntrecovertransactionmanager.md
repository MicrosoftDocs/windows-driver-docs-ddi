---
UID: NF:wdm.NtRecoverTransactionManager
title: NtRecoverTransactionManager function
author: windows-driver-content
description: The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.
old-location: kernel\zwrecovertransactionmanager.htm
tech.root: kernel
ms.assetid: 20284cad-5d65-4d22-98fa-6b6c5f6b422d
ms.date: 04/30/2018
ms.keywords: NtRecoverTransactionManager, ZwRecoverTransactionManager, ZwRecoverTransactionManager routine [Kernel-Mode Driver Architecture], kernel.zwrecovertransactionmanager, ktm_ref_8ff406ba-2e7b-453e-8fc7-12e88a3bf41e.xml, wdm/NtRecoverTransactionManager, wdm/ZwRecoverTransactionManager
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
-	ZwRecoverTransactionManager
-	NtRecoverTransactionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtRecoverTransactionManager function


## -description


The <b>ZwRecoverTransactionManager</b> routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.


## -parameters




### -param TransactionManagerHandle [in]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567035">ZwOpenTransactionManager</a>. The handle must have TRANSACTIONMANAGER_RECOVER access to the object.


## -returns



<b>ZwRecoverTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:

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
The specified handle is not a handle to a transaction manager object.

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
The caller does not have appropriate access to the transaction manager object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>
</td>
<td width="60%">
The transaction manager object is volatile and, therefore, its transactions cannot be recovered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The transaction manager object is not in a state that allows recovery.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>ZwRecoverTransactionManager</b> routine tries to reconstruct the state of the transaction manager object, including all transactions, enlistments, and resource managers, from the recovery information that is in the object's log stream, beginning at the last <a href="https://msdn.microsoft.com/310545f6-d10d-481e-829d-287b045b98cd">restart area</a> that KTM created and ending at the stream's end.

To recover up to a specific virtual time, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567089">ZwRollforwardTransactionManager</a> routine instead of <b>ZwRecoverTransactionManager</b>.

Your TPS component must call <b>ZwRecoverTransactionManager</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567035">ZwOpenTransactionManager</a>.

For more information about recovery operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

<b>NtRecoverTransactionManager</b> and <b>ZwRecoverTransactionManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564722">TmRecoverTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567035">ZwOpenTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567089">ZwRollforwardTransactionManager</a>
 

 

