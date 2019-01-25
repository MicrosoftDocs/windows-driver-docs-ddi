---
UID: NF:fltkernel.FltGetTransactionContext
title: FltGetTransactionContext function (fltkernel.h)
description: The FltGetTransactionContext routine retrieves a context that was set for a transaction by a given minifilter driver.
old-location: ifsk\fltgettransactioncontext.htm
tech.root: ifsk
ms.assetid: fcd41baf-43ff-4f3a-8211-9fb5cb1cd2fd
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_11458006-a870-473b-9d1b-ab7a97af09b3.xml, FltGetTransactionContext, FltGetTransactionContext routine [Installable File System Drivers], fltkernel/FltGetTransactionContext, ifsk.fltgettransactioncontext
ms.topic: function
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
-	FltGetTransactionContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetTransactionContext function


## -description


The <b>FltGetTransactionContext</b> routine retrieves a context that was set for a transaction by a given minifilter driver. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param Transaction [in]

Opaque transaction pointer for the transaction whose context is being retrieved. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the transaction context. 


## -returns



<b>FltGetTransactionContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
No matching context was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetTransactionContext</b> is available on Windows Vista and later. 

<b>FltGetTransactionContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. Thus every successful call to <b>FltGetTransactionContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a transaction, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>. 

To allocate a new transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544374">FltRollbackEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>
 

 

