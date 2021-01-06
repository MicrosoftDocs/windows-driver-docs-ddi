---
UID: NC:fltkernel.PFLT_TRANSACTION_NOTIFICATION_CALLBACK
title: PFLT_TRANSACTION_NOTIFICATION_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its TransactionNotificationCallback routine.
old-location: ifsk\pflt_transaction_notification_callback.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback function"]
ms.keywords: FltCallbacks_e4045561-4dc3-44eb-b5c6-086e767f9c22.xml, PFLT_TRANSACTION_NOTIFICATION_CALLBACK, TransactionNotificationCallback, TransactionNotificationCallback routine [Installable File System Drivers], fltkernel/TransactionNotificationCallback, ifsk.pflt_transaction_notification_callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: The PFLT_TRANSACTION_NOTIFICATION_CALLBACK routine is available on Windows Vista and later.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_TRANSACTION_NOTIFICATION_CALLBACK
 - fltkernel/PFLT_TRANSACTION_NOTIFICATION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - TransactionNotificationCallback
---

# PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback function


## -description

A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its <i>TransactionNotificationCallback</i> routine.

## -parameters

### -param FltObjects 

[in]
Pointer to an <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation.

### -param TransactionContext 

[in]
Pointer to the minifilter driver's transaction context.

### -param NotificationMask 

[in]
Specifies the type of notifications that the filter manager is sending to the minifilter driver, as one of the following values. 

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
For Windows Vista SP1 and later, this notification is sent when the transaction is fully committed (that is, when all of the <a href="/previous-versions//aa365519(v=vs.85)">resource managers</a> associated with the transaction, such as <a href="https://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed).

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPARE

</td>
<td>
This notification is sent when the transaction enters the prepare for commit phase. 

</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPREPARE

</td>
<td>
This notification is sent when the transaction enters the pre-prepare for commit phase. 

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
</table>

## -returns

The PFLT_TRANSACTION_NOTIFICATION_CALLBACK routine returns one of the following NTSTATUS values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Returning this status value indicates that the minifilter driver is finished with the transaction. This is a success code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Returning this status value indicates that the minifilter driver is not yet finished with the transaction. This is a success code. 

</td>
</tr>
</table>

## -remarks

When a minifilter driver registers itself by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a> from its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, it can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as the minifilter's <i>TransactionNotificationCallback</i> routine. 

To register the <i>TransactionNotificationCallback</i> routine, the minifilter driver stores the address of a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK in the <b>TransactionNotificationCallback</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <b>FltRegisterFilter</b>. 

The filter manager calls this routine to notify the minifilter driver about the status of a transaction that the minifilter driver is enlisted in. 

If the minifilter driver returns STATUS_PENDING from this callback routine, it must eventually call one of the following routines to indicate that it has finished processing the notification: 


<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcommitcomplete">FltCommitComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparecomplete">FltPrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltprepreparecomplete">FltPrePrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrollbackcomplete">FltRollbackComplete</a>

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcommitcomplete">FltCommitComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltprepreparecomplete">FltPrePrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparecomplete">FltPrepareComplete</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrollbackcomplete">FltRollbackComplete</a>
