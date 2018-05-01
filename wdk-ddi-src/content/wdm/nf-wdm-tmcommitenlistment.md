---
UID: NF:wdm.TmCommitEnlistment
title: TmCommitEnlistment function
author: windows-driver-content
description: The TmCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction.
old-location: kernel\tmcommitenlistment.htm
old-project: kernel
ms.assetid: f1f0c337-9567-4def-b0fb-09dabfdf294d
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: TmCommitEnlistment, TmCommitEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmcommitenlistment, ktm_ref_c34bfdb9-5d62-448c-a82f-a8df21f05371.xml, wdm/TmCommitEnlistment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
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
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmCommitEnlistment
product: Windows
targetos: Windows
req.typenames: 
---

# TmCommitEnlistment function


## -description


The <b>TmCommitEnlistment</b> routine initiates the commit operation for a specified enlistment's transaction.


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>TmCommitEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
The enlistment's transaction is not in a state that enables it to be committed.

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



The <b>TmCommitEnlistment</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566419">ZwCommitEnlistment</a> routine.

Only superior transaction managers can call <b>TmCommitEnlistment</b>.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566419">ZwCommitEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>
 

 

