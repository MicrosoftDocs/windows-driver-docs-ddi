---
UID: NF:fltkernel.FltDeleteTransactionContext
title: FltDeleteTransactionContext function
author: windows-driver-content
description: The FltDeleteTransactionContext routine removes a context from a given transaction and marks the context for deletion.
old-location: ifsk\fltdeletetransactioncontext.htm
old-project: ifsk
ms.assetid: 120285ff-1cb4-4570-a1e7-0a7d22b43560
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_785d668e-0232-4937-996e-846e459db2c5.xml, FltDeleteTransactionContext, FltDeleteTransactionContext routine [Installable File System Drivers], fltkernel/FltDeleteTransactionContext, ifsk.fltdeletetransactioncontext
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDeleteTransactionContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeleteTransactionContext function


## -description


The <b>FltDeleteTransactionContext</b> routine removes a context from a given transaction and marks the context for deletion. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param Transaction [in]

Opaque transaction pointer for the transaction whose context is being deleted. 


### -param OldContext [out, optional]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns



<b>FltDeleteTransactionContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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



This routine is available on Windows Vista and later. 

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteTransactionContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteTransactionContext</b> to remove a context from a transaction and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

To allocate a new transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>. 

To set a transaction context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541875">FltCommitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542053">FltEnlistInTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543425">FltPrePrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543424">FltPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544366">FltRollbackComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544374">FltRollbackEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>
 

 

