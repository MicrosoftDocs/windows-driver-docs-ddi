---
UID: NF:fltkernel.FltEnlistInTransaction
title: FltEnlistInTransaction function
author: windows-driver-content
description: The FltEnlistInTransaction routine enlists a minifilter driver in a given transaction.
old-location: ifsk\fltenlistintransaction.htm
old-project: ifsk
ms.assetid: c4b82596-824f-488e-96cd-17bd850494e5
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_85856df2-46c0-457b-bc10-2e6a8d32f5bb.xml, FltEnlistInTransaction, FltEnlistInTransaction routine [Installable File System Drivers], fltkernel/FltEnlistInTransaction, ifsk.fltenlistintransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later versions of Windows.
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
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltEnlistInTransaction
product: Windows
targetos: Windows
req.typenames: 
---

# FltEnlistInTransaction function


## -description


The <b>FltEnlistInTransaction</b> routine enlists a minifilter driver in a given transaction. 


## -parameters




### -param Instance [in]

An opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Transaction [in]

An opaque transaction pointer for the transaction. 


### -param TransactionContext [in]

A pointer to the minifilter driver's transaction context. This parameter is required and cannot be <b>NULL</b>. 


### -param NotificationMask [in]

Specifies the type of notifications that the filter manager is to send to the minifilter driver, as one or more of the values listed in the following table. This parameter is required and cannot be zero. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_COMMIT

</td>
<td>
This notification is sent when the transaction is being committed. 

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_COMMIT_FINALIZE

</td>
<td>
For Windows Vista SP1 and later, this notification is sent when the transaction is fully committed (that is, when all of the <a href="http://go.microsoft.com/fwlink/p/?linkid=94490">resource managers</a> associated with the transaction, such as <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed).

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPARE

</td>
<td>
This notification is sent when the transaction has entered the prepare for commit phase. 

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPREPARE

</td>
<td>
This notification is sent when the transaction has entered the pre-prepare for commit phase. 

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_ROLLBACK

</td>
<td>
This notification is sent when the transaction is being rolled back or aborted. 

</td>
</tr>
<tr>
<td>
FLT_MAX_TRANSACTION_NOTIFICATIONS

</td>
<td>
TRANSACTION_NOTIFY_COMMIT | TRANSACTION_NOTIFY_PREPARE | TRANSACTION_NOTIFY_PREPREPARE | TRANSACTION_NOTIFY_ROLLBACK 

</td>
</tr>
</table>
 


## -returns



<b>FltEnlistInTransaction</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_ALREADY_ENLISTED</b></dt>
</dl>
</td>
<td width="60%">
The caller is already enlisted in the transaction. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance specified in the <i>Instance</i> parameter is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltEnlistInTransaction</b> encountered a pool allocation error. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller did not register a <i>TransactionNotificationCallback</i> routine. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for the <i>NotificationMask</i> parameter. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltEnlistInTransaction</b> to enlist in a transaction. Before calling <b>FltEnlistInTransaction</b>, the minifilter driver must have registered a <i>TransactionNotificationCallback</i> routine. Otherwise, the call to <b>FltEnlistInTransaction</b> will fail. 

To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551121">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 

To roll back or abort a transaction, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544374">FltRollbackEnlistment</a>. 

To allocate a new transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To set a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544374">FltRollbackEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551121">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>
 

 

