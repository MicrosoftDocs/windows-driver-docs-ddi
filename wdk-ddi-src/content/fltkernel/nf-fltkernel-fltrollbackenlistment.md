---
UID: NF:fltkernel.FltRollbackEnlistment
title: FltRollbackEnlistment function
author: windows-driver-content
description: The FltRollbackEnlistment routine rolls back or aborts a transaction on behalf of a minifilter driver.
old-location: ifsk\fltrollbackenlistment.htm
old-project: ifsk
ms.assetid: a63ebd95-801b-4de2-963e-392e6d90eb9f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltrollbackenlistment, FltRollbackEnlistment, FltApiRef_p_to_z_f59e0c07-d415-440b-aec8-89c330679e0d.xml, fltkernel/FltRollbackEnlistment, FltRollbackEnlistment routine [Installable File System Drivers]
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltRollbackEnlistment
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltRollbackEnlistment function


## -description


The <b>FltRollbackEnlistment</b> routine rolls back or aborts a transaction on behalf of a minifilter driver. 


## -syntax


````
NTSTATUS FltRollbackEnlistment(
  _In_     PFLT_INSTANCE Instance,
  _In_     PKTRANSACTION Transaction,
  _In_opt_ PFLT_CONTEXT  TransactionContext
);
````


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

To enlist in a transaction, call <a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>. 

To allocate a new transaction context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To set a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>



<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRollbackEnlistment routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

