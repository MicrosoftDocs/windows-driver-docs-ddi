---
UID: NF:fltkernel.FltCommitFinalizeComplete
title: FltCommitFinalizeComplete function (fltkernel.h)
description: The FltCommitFinalizeComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification.
old-location: ifsk\fltcommitfinalizecomplete.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltCommitFinalizeComplete function"]
ms.keywords: FltApiRef_a_to_d_f2b874db-f5fb-405b-a3a5-b5877c88548d.xml, FltCommitFinalizeComplete, FltCommitFinalizeComplete routine [Installable File System Drivers], fltkernel/FltCommitFinalizeComplete, ifsk.fltcommitfinalizecomplete
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista Service Pack 1 (SP1) and later.
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCommitFinalizeComplete
 - fltkernel/FltCommitFinalizeComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fltmgr.lib
 - Fltmgr.dll
api_name:
 - FltCommitFinalizeComplete
---

# FltCommitFinalizeComplete function


## -description

The <b>FltCommitFinalizeComplete</b> routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification.

## -parameters

### -param Instance 

[in]
Opaque pointer to an instance of a minifilter driver. This parameter is required and cannot be <b>NULL</b>.

### -param Transaction 

[in]
Opaque pointer to the transaction the minifilter driver is currently enlisted in. This parameter is required and cannot be <b>NULL</b>.

### -param TransactionContext 

[in, optional]
Pointer to the minifilter driver's context for the transaction. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>FltCommitFinalizeComplete</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver did not set a context on the transaction. This is an error code. 

</td>
</tr>
</table>

## -remarks

A minifilter driver that is enlisted in a transaction can receive a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification when the transaction is fully committed (that is, when all of the <a href="/previous-versions//aa365519(v=vs.85)">resource managers</a> associated with the transaction, such as <a href="https://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed). For an antivirus minifilter driver that performs scans outside of transactions, you can use this notification value to determine when the driver should begin scanning files.

To send the TRANSACTION_NOTIFY_COMMIT_FINALIZE notification to the minifilter driver, the filter manager calls the minifilter driver's <i>TransactionNotificationCallback</i> routine. The minifilter driver acknowledges this notification in one of two ways:

<ul>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine performs any required processing and returns STATUS_SUCCESS. (In this case, the minifilter driver does not call <b>FltCommitFinalizeComplete</b>.)

</li>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine posts any required processing to a worker thread and returns STATUS_PENDING. After performing the processing asynchronously, the minifilter driver's worker thread routine must call <b>FltCommitFinalizeComplete</b> to indicate that it has finished this processing. If the minifilter driver's worker thread routine does not call <b>FltCommitFinalizeComplete</b>, certain system resources will be leaked.

</li>
</ul>
To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_transaction_notification_callback">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>. 

To enlist in a transaction, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenlistintransaction">FltEnlistInTransaction</a>.

To allocate a new transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgettransactioncontext">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletetransactioncontext">FltDeleteTransactionContext</a> or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To set a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsettransactioncontext">FltSetTransactionContext</a>. 

For more information, see <a href="/windows-hardware/drivers/kernel/transaction-notifications">Transaction Notifications</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcommitcomplete">FltCommitComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletetransactioncontext">FltDeleteTransactionContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenlistintransaction">FltEnlistInTransaction</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgettransactioncontext">FltGetTransactionContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltprepreparecomplete">FltPrePrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparecomplete">FltPrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrollbackcomplete">FltRollbackComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrollbackenlistment">FltRollbackEnlistment</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsettransactioncontext">FltSetTransactionContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_transaction_notification_callback">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>
