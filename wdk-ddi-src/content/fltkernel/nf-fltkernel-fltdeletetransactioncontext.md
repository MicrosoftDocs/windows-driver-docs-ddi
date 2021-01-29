---
UID: NF:fltkernel.FltDeleteTransactionContext
title: FltDeleteTransactionContext function (fltkernel.h)
description: The FltDeleteTransactionContext routine removes a context from a given transaction and marks the context for deletion.
old-location: ifsk\fltdeletetransactioncontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteTransactionContext function"]
ms.keywords: FltApiRef_a_to_d_785d668e-0232-4937-996e-846e459db2c5.xml, FltDeleteTransactionContext, FltDeleteTransactionContext routine [Installable File System Drivers], fltkernel/FltDeleteTransactionContext, ifsk.fltdeletetransactioncontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista and later
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDeleteTransactionContext
 - fltkernel/FltDeleteTransactionContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteTransactionContext
---

# FltDeleteTransactionContext function

## -description

The **FltDeleteTransactionContext** routine removes a context from a given transaction and marks the context for deletion.

## -parameters

### -param Instance

[in] Opaque instance pointer for the caller.

### -param Transaction

[in] Opaque transaction pointer for the transaction whose context is being deleted.

### -param OldContext

[out, optional] Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be **NULL**. If *OldContext* is not **NULL** and does not point to NULL_CONTEXT, the caller is responsible for calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to release this context when it is no longer needed.

## -returns

**FltDeleteTransactionContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified *Instance* is being torn down. This is an error code. |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as **FltDeleteTransactionContext** to explicitly delete a context.

A minifilter driver calls **FltDeleteTransactionContext** to remove a context from a transaction and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To retrieve a transaction context, call [**FltGetTransactionContext**](nf-fltkernel-fltgettransactioncontext.md).

To set a transaction context, call [**FltSetTransactionContext**](nf-fltkernel-fltsettransactioncontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltCommitComplete**](nf-fltkernel-fltcommitcomplete.md)

[**FltEnlistInTransaction**](nf-fltkernel-fltenlistintransaction.md)

[**FltGetTransactionContext**](nf-fltkernel-fltgettransactioncontext.md)

[**FltPrePrepareComplete**](nf-fltkernel-fltprepreparecomplete.md)

[**FltPrepareComplete**](nf-fltkernel-fltpreparecomplete.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltRollbackComplete**](nf-fltkernel-fltrollbackcomplete.md)

[**FltRollbackEnlistment**](nf-fltkernel-fltrollbackenlistment.md)

[**FltSetTransactionContext**](nf-fltkernel-fltsettransactioncontext.md)
