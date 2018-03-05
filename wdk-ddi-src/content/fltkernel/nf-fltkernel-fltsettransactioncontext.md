---
UID: NF:fltkernel.FltSetTransactionContext
title: FltSetTransactionContext function
author: windows-driver-content
description: The FltSetTransactionContext routine sets a context on a transaction.
old-location: ifsk\fltsettransactioncontext.htm
old-project: ifsk
ms.assetid: bb68ee38-1726-4493-9c3b-71a1352dd9f2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FLT_SET_CONTEXT_KEEP_IF_EXISTS, FLT_SET_CONTEXT_REPLACE_IF_EXISTS, FltApiRef_p_to_z_ac2c79a4-ca14-417d-a394-24a38d89f3bf.xml, FltSetTransactionContext, FltSetTransactionContext routine [Installable File System Drivers], fltkernel/FltSetTransactionContext, ifsk.fltsettransactioncontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Windows Vista and later operating systems.
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
req.irql: "<= APC_LEVEL."
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltSetTransactionContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetTransactionContext function


## -description


The <b>FltSetTransactionContext</b> routine sets a context on a transaction. 


## -syntax


````
NTSTATUS FltSetTransactionContext(
  _In_      PFLT_INSTANCE             Instance,
  _In_      PKTRANSACTION             Transaction,
  _In_      FLT_SET_CONTEXT_OPERATION Operation,
  _In_      PFLT_CONTEXT              NewContext,
  _Out_opt_ PFLT_CONTEXT              *OldContext
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param Transaction [in]

Opaque transaction pointer for the transaction on which the context is being set. 


### -param Operation [in]

Flag that specifies the details of the operation to be performed. This parameter must be one of the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FLT_SET_CONTEXT_REPLACE_IF_EXISTS"></a><a id="flt_set_context_replace_if_exists"></a><dl>
<dt><b>FLT_SET_CONTEXT_REPLACE_IF_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
If a context is already set for the transaction pointed to by the <i>Transaction</i> parameter, replace the existing context with the context pointed to by the <i>NewContext</i> parameter. Otherwise, set the context pointed to by the <i>NewContext</i> parameter as the context for the transaction pointed to by the <i>Transaction</i> parameter. 

</td>
</tr>
<tr>
<td width="40%"><a id="FLT_SET_CONTEXT_KEEP_IF_EXISTS"></a><a id="flt_set_context_keep_if_exists"></a><dl>
<dt><b>FLT_SET_CONTEXT_KEEP_IF_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
If a context is already set for the transaction pointed to by the <i>Transaction</i> parameter, return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, set the context pointed to by the <i>NewContext</i> parameter as the context for transaction pointed to by the <i>Transaction</i> parameter. 

</td>
</tr>
</table>
 


### -param NewContext [in]

Pointer to the new context to be set for the instance. The context must have been allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out, optional]

Pointer to a caller-allocated variable that receives the address of the existing transaction context, if one is already set. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


## -returns



<b>FltSetTransactionContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>
</td>
<td width="60%">
If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for the <i>Operation</i> parameter, this error code indicates that a context is already attached to the transaction. Only one context can be attached to a transaction for a given minifilter driver. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>
</td>
<td width="60%">
The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of an <b>FltSet</b><i>Xxx</i><b>Context</b> routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance specified in the Instance parameter is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
STATUS_INVALID_PARAMETER

One of the following:

<ul>
<li>The <i>NewContext</i> parameter does not point to a valid transaction context. </li>
<li>An invalid value was specified for the <i>Operation</i> parameter. </li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltSetTransactionContext</b> to attach a context to a transaction or to remove or replace an existing transaction context. A minifilter driver can attach only one context to a given transaction. 

Before calling <b>FltSetTransactionContext</b> to set a new transaction context, the caller must call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a> to allocate the context object. 

A successful call to <b>FltSetTransactionContext</b> increments the reference count on <i>NewContext</i>. If <b>FltSetTransactionContext</b> fails, the reference count remains unchanged. In either case, the filter calling <b>FltSetTransactionContext</b> must call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to decrement the <i>NewContext</i> object. If <b>FltSetTransactionContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetTransactionContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.

Note that the <i>OldContext</i> pointer returned by <b>FltSetTransactionContext</b> must also be released by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="https://msdn.microsoft.com/3daa23e6-14d7-4d35-8bc8-695296cd289d">Setting Contexts</a> and <a href="https://msdn.microsoft.com/29d855cd-cca6-486b-86d9-f74810ae12c1">Releasing Contexts</a>. 

To retrieve a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>. 

To allocate a new transaction context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>



<a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackenlistment.md">FltRollbackEnlistment</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetTransactionContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

