---
UID: NF:fltkernel.FltRollbackEnlistment
title: FltRollbackEnlistment function
description: The FltRollbackEnlistment routine rolls back or aborts a transaction on behalf of a minifilter driver.
old-location: ifsk\fltrollbackenlistment.htm
tech.root: ifsk
ms.assetid: a63ebd95-801b-4de2-963e-392e6d90eb9f
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_f59e0c07-d415-440b-aec8-89c330679e0d.xml, FltRollbackEnlistment, FltRollbackEnlistment routine [Installable File System Drivers], fltkernel/FltRollbackEnlistment, ifsk.fltrollbackenlistment
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltRollbackEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRollbackEnlistment function


## -description


The <b>FltRollbackEnlistment</b> routine rolls back or aborts a transaction on behalf of a minifilter driver. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param Transaction [in]

Opaque transaction pointer for the transaction. 


### -param TransactionContext [in, optional]

Pointer to the minifilter driver's transaction context. 


## -returns



<b>FltRollbackEnlistment</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The transaction rollback request is not allowed for this enlistment. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver that is enlisted in a transaction can call <b>FltRollbackEnlistment</b> to roll back or abort the transaction. 

To enlist in a transaction, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>. 

To allocate a new transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To set a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>
 

 

