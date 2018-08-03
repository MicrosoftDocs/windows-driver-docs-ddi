---
UID: NF:fltkernel.FltRollbackComplete
title: FltRollbackComplete function
author: windows-driver-content
description: The FltRollbackComplete routine acknowledges a TRANSACTION_NOTIFY_ROLLBACK notification.
old-location: ifsk\fltrollbackcomplete.htm
tech.root: ifsk
ms.assetid: 822d3ed1-66ce-48a8-924c-48e1082cbb25
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_5a4ebf97-8580-437d-b34d-e873bad7161b.xml, FltRollbackComplete, FltRollbackComplete routine [Installable File System Drivers], fltkernel/FltRollbackComplete, ifsk.fltrollbackcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later.
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
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltRollbackComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRollbackComplete function


## -description


The <b>FltRollbackComplete</b> routine acknowledges a TRANSACTION_NOTIFY_ROLLBACK notification. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param Transaction [in]

Opaque transaction pointer for the transaction. 


### -param TransactionContext [in, optional]

Pointer to the minifilter driver's transaction context. 


## -returns



<b>FltRollbackComplete</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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



A minifilter driver that is enlisted in a transaction can receive a TRANSACTION_NOTIFY_ROLLBACK notification when the transaction is in the process of being rolled back or aborted. To send the notification to the minifilter driver, the filter manager calls the minifilter driver's <i>TransactionNotificationCallback</i> routine. The minifilter driver acknowledges this notification in one of two ways: 

<ul>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine performs any needed processing and returns STATUS_SUCCESS. In this case, the minifilter driver does not call <b>FltRollbackComplete</b>. 

</li>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine posts any needed processing to a worker thread and returns STATUS_PENDING. After performing the processing asynchronously, the minifilter driver's work routine must call <b>FltRollbackComplete</b> to indicate that it has finished this processing. If the minifilter driver's work routine does not call <b>FltRollbackComplete</b>, the transaction rollback or abort operation cannot be completed by the kernel transaction manager. 

</li>
</ul>
To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551121">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 

To enlist in a transaction, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>. 

To allocate a new transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To set a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544374">FltRollbackEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551121">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>
 

 

