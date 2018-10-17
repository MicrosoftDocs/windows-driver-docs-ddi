---
UID: NF:wdm.NtCommitEnlistment
title: NtCommitEnlistment function
author: windows-driver-content
description: The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction.
old-location: kernel\zwcommitenlistment.htm
tech.root: kernel
ms.assetid: 9c7f3e24-1d7c-450e-bbef-df0479911bc6
ms.date: 4/30/2018
ms.keywords: NtCommitEnlistment, ZwCommitEnlistment, ZwCommitEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwcommitenlistment, ktm_ref_b99f9962-ce40-4324-9482-b8202d96425d.xml, wdm/NtCommitEnlistment, wdm/ZwCommitEnlistment
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
-	ZwCommitEnlistment
-	NtCommitEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtCommitEnlistment function


## -description


The <b>ZwCommitEnlistment</b> routine initiates the commit operation for a specified enlistment's transaction.


## -parameters




### -param EnlistmentHandle [in]

A handle to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>. The object must represent a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior enlistment</a> and the handle must have ENLISTMENT_SUPERIOR_RIGHTS access to the object.


### -param TmVirtualClock [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwCommitEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The specified handle is not a handle to an enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_SUPERIOR</b></dt>
</dl>
</td>
<td width="60%">
The caller is not a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> for the enlistment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_RESPONSE_NOT_ENLISTED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not register to receive TRANSACTION_NOTIFY_COMMIT_COMPLETE notifications.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The enlistment's transaction is not in a state that allows it to be committed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_NOT_ACTIVE</b></dt>
</dl>
</td>
<td width="60%">
The commit operation for this transaction has already been started.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction cannot be committed because it has been rolled back.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Only superior transaction managers can call <b>ZwCommitEnlistment</b>.

Callers of <b>ZwCommitEnlistment</b> must register to receive TRANSACTION_NOTIFY_COMMIT_COMPLETE <a href="https://msdn.microsoft.com/library/windows/hardware/mt244308">notifications</a>.

The <b>ZwCommitEnlistment</b> routine causes KTM to send TRANSACTION_NOTIFY_COMMIT notifications to all resource managers that have enlisted in the transaction.

For more information about <b>ZwCommitEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542870">Creating a Superior Transaction Manager</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff546783">Handling Commit Operations</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564661">TmCommitEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>
 

 

