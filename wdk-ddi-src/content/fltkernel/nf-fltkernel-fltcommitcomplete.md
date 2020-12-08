---
UID: NF:fltkernel.FltCommitComplete
title: FltCommitComplete function (fltkernel.h)
description: The FltCommitComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT notification.
old-location: ifsk\fltcommitcomplete.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltCommitComplete function"]
ms.keywords: FltApiRef_a_to_d_fc4b72a5-52df-47f9-b119-68ccb02b14bc.xml, FltCommitComplete, FltCommitComplete routine [Installable File System Drivers], fltkernel/FltCommitComplete, ifsk.fltcommitcomplete
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCommitComplete
 - fltkernel/FltCommitComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fltmgr.lib
 - Fltmgr.dll
api_name:
 - FltCommitComplete
---

# FltCommitComplete function


## -description

The <b>FltCommitComplete</b> routine acknowledges a TRANSACTION_NOTIFY_COMMIT notification.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the caller.

### -param Transaction 

[in]
Opaque transaction pointer for the transaction.

### -param TransactionContext 

[in, optional]
Pointer to the minifilter driver's context for the transaction. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>FltCommitComplete</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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

This routine is available on Windows Vista and later. 

A minifilter driver that is enlisted in a transaction can receive a TRANSACTION_NOTIFY_COMMIT notification when the transaction is in the process of being committed. To send the notification to the minifilter driver, the filter manager calls the minifilter driver's <b>TransactionNotificationCallback</b> routine. The minifilter driver acknowledges this notification in one of two ways: 

<ul>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine performs any needed processing and returns STATUS_SUCCESS. In this case, the minifilter driver does not call <b>FltCommitComplete</b>. 

</li>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine posts any needed processing to a worker thread and returns STATUS_PENDING. After performing the processing asynchronously, the minifilter driver's work routine must call <b>FltCommitComplete</b> to indicate that it has finished this processing. If the minifilter driver's work routine does not call <b>FltCommitComplete</b>, the transaction commit operation cannot be completed by the kernel transaction manager. 

</li>
</ul>
To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_transaction_notification_callback">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>. 

To enlist in a transaction, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenlistintransaction">FltEnlistInTransaction</a>.

To allocate a new transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgettransactioncontext">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletetransactioncontext">FltDeleteTransactionContext</a> or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To set a transaction context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsettransactioncontext">FltSetTransactionContext</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



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
