---
UID: NC:fltkernel.PFLT_TRANSACTION_NOTIFICATION_CALLBACK
title: PFLT_TRANSACTION_NOTIFICATION_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its TransactionNotificationCallback routine.
old-location: ifsk\pflt_transaction_notification_callback.htm
old-project: ifsk
ms.assetid: ed441ca2-ca98-4c8c-9c2f-4258c535ebac
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: The PFLT_TRANSACTION_NOTIFICATION_CALLBACK routine is available on Windows Vista and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TransactionNotificationCallback
req.alt-loc: fltkernel.h
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
req.typenames: EXpsFontRestriction
---

# PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback



## -description
A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its <i>TransactionNotificationCallback</i> routine. 



## -prototype

````
PFLT_TRANSACTION_NOTIFICATION_CALLBACK TransactionNotificationCallback;

NTSTATUS TransactionNotificationCallback(
  _In_ PCFLT_RELATED_OBJECTS FltObjects,
  _In_ PFLT_CONTEXT          TransactionContext,
  _In_ ULONG                 NotificationMask
)
{ ... }
````


## -parameters

### -param FltObjects [in]

Pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation. 


### -param TransactionContext [in]

Pointer to the minifilter driver's transaction context. 


### -param NotificationMask [in]

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
For Windows Vista SP1 and later, this notification is sent when the transaction is fully committed (that is, when all of the <a href="http://go.microsoft.com/fwlink/p/?linkid=94490">resource managers</a> associated with the transaction, such as <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed).

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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Returning this status value indicates that the minifilter driver is finished with the transaction. This is a success code. 
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>Returning this status value indicates that the minifilter driver is not yet finished with the transaction. This is a success code. 

 


## -remarks
When a minifilter driver registers itself by calling <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine, it can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as the minifilter's <i>TransactionNotificationCallback</i> routine. 

To register the <i>TransactionNotificationCallback</i> routine, the minifilter driver stores the address of a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK in the <b>TransactionNotificationCallback</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <b>FltRegisterFilter</b>. 

The filter manager calls this routine to notify the minifilter driver about the status of a transaction that the minifilter driver is enlisted in. 

If the minifilter driver returns STATUS_PENDING from this callback routine, it must eventually call one of the following routines to indicate that it has finished processing the notification: 


<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>



## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_TRANSACTION_NOTIFICATION_CALLBACK routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

