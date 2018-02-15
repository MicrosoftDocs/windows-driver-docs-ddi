---
UID: NF:wdm.TmCommitTransaction
title: TmCommitTransaction function
author: windows-driver-content
description: The TmCommitTransaction routine initiates a commit operation for a specified transaction.
old-location: kernel\tmcommittransaction.htm
old-project: kernel
ms.assetid: 8d17de44-2fd9-4e20-8a9b-2647c9917709
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/TmCommitTransaction, TmCommitTransaction routine [Kernel-Mode Driver Architecture], kernel.tmcommittransaction, TmCommitTransaction, ktm_ref_e5e36a40-1ee7-469c-acd9-8e7a44017853.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname:
-	TmCommitTransaction
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmCommitTransaction function


## -description


The <b>TmCommitTransaction</b> routine initiates a commit operation for a specified transaction.


## -syntax


````
NTSTATUS TmCommitTransaction(
  _In_ PKTRANSACTION Transaction,
  _In_ BOOLEAN       Wait
);
````


## -parameters




### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your TPS component must call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a> provided.


### -param Wait [in]

A Boolean value that the caller sets to <b>TRUE</b> for synchronous operation or <b>FALSE</b> for asynchronous operation. If this parameter is <b>TRUE</b>, the call returns after the commit operation is complete.


## -returns



<b>TmCommitTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_SUPERIOR_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot commit the transaction because a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> exists.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_COMMITTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction is already committed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The commit operation for this transaction has already been started.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Commit notifications have been queued to resource managers, and the caller specified <b>FALSE</b> for the <i>Wait</i> parameter.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmCommitTransaction</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a>



<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmCommitTransaction routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

