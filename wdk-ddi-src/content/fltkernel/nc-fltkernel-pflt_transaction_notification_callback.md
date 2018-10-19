---
UID: NC:fltkernel.PFLT_TRANSACTION_NOTIFICATION_CALLBACK
title: PFLT_TRANSACTION_NOTIFICATION_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its TransactionNotificationCallback routine.
old-location: ifsk\pflt_transaction_notification_callback.htm
tech.root: ifsk
ms.assetid: ed441ca2-ca98-4c8c-9c2f-4258c535ebac
ms.date: 04/16/2018
ms.keywords: FltCallbacks_e4045561-4dc3-44eb-b5c6-086e767f9c22.xml, PFLT_TRANSACTION_NOTIFICATION_CALLBACK, TransactionNotificationCallback, TransactionNotificationCallback routine [Installable File System Drivers], fltkernel/TransactionNotificationCallback, ifsk.pflt_transaction_notification_callback
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	TransactionNotificationCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback function


## -description


A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its <i>TransactionNotificationCallback</i> routine. 


## -parameters




### -param FltObjects [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation. 


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



When a minifilter driver registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, it can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as the minifilter's <i>TransactionNotificationCallback</i> routine. 

To register the <i>TransactionNotificationCallback</i> routine, the minifilter driver stores the address of a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK in the <b>TransactionNotificationCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <b>FltRegisterFilter</b>. 

The filter manager calls this routine to notify the minifilter driver about the status of a transaction that the minifilter driver is enlisted in. 

If the minifilter driver returns STATUS_PENDING from this callback routine, it must eventually call one of the following routines to indicate that it has finished processing the notification: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>
 

 

