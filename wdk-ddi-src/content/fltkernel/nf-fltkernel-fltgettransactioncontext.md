---
UID: NF:fltkernel.FltGetTransactionContext
title: FltGetTransactionContext function (fltkernel.h)
description: The FltGetTransactionContext routine retrieves a context that was set for a transaction by a given minifilter driver.
old-location: ifsk\fltgettransactioncontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltGetTransactionContext function"]
ms.keywords: FltApiRef_e_to_o_11458006-a870-473b-9d1b-ab7a97af09b3.xml, FltGetTransactionContext, FltGetTransactionContext routine [Installable File System Drivers], fltkernel/FltGetTransactionContext, ifsk.fltgettransactioncontext
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetTransactionContext
 - fltkernel/FltGetTransactionContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltGetTransactionContext
---

# FltGetTransactionContext function

## -description

The **FltGetTransactionContext** routine retrieves a context that was set for a transaction by a given minifilter driver.

## -parameters

### -param Instance

[in] Opaque instance pointer for the caller.

### -param Transaction

[in] Opaque transaction pointer for the transaction whose context is being retrieved.

### -param Context

[out] Pointer to a caller-allocated variable that receives the address of the transaction context.

## -returns

**FltGetTransactionContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetTransactionContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetTransactionContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a context for a transaction, call [**FltSetTransactionContext**](nf-fltkernel-fltsettransactioncontext.md).

To allocate a new transaction context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a transaction context, call [**FltDeleteTransactionContext**](nf-fltkernel-fltdeletetransactioncontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltCommitComplete**](nf-fltkernel-fltcommitcomplete.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteTransactionContext**](nf-fltkernel-fltdeletetransactioncontext.md)

[**FltEnlistInTransaction**](nf-fltkernel-fltenlistintransaction.md)

[**FltPrePrepareComplete**](nf-fltkernel-fltprepreparecomplete.md)

[**FltPrepareComplete**](nf-fltkernel-fltpreparecomplete.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltRollbackComplete**](nf-fltkernel-fltrollbackcomplete.md)

[**FltRollbackEnlistment**](nf-fltkernel-fltrollbackenlistment.md)

[**FltSetTransactionContext**](nf-fltkernel-fltsettransactioncontext.md)
