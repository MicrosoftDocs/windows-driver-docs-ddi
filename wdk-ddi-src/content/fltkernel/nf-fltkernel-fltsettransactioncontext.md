---
UID: NF:fltkernel.FltSetTransactionContext
title: FltSetTransactionContext function (fltkernel.h)
description: The FltSetTransactionContext routine sets a context on a transaction.
old-location: ifsk\fltsettransactioncontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltSetTransactionContext function"]
ms.keywords: FLT_SET_CONTEXT_KEEP_IF_EXISTS, FLT_SET_CONTEXT_REPLACE_IF_EXISTS, FltApiRef_p_to_z_ac2c79a4-ca14-417d-a394-24a38d89f3bf.xml, FltSetTransactionContext, FltSetTransactionContext routine [Installable File System Drivers], fltkernel/FltSetTransactionContext, ifsk.fltsettransactioncontext
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
req.irql: <= APC_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSetTransactionContext
 - fltkernel/FltSetTransactionContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltSetTransactionContext
---

# FltSetTransactionContext function

## -description

The **FltSetTransactionContext** routine sets a context on a transaction.

## -parameters

### -param Instance

[in] Opaque instance pointer for the caller.

### -param Transaction

[in] Opaque transaction pointer for the transaction on which the context is being set.

### -param Operation

[in] Flag that specifies the details of the operation to be performed. This parameter must be one of the following:

| Flag | Meaning |
| ---- | ------- |
| FLT_SET_CONTEXT_REPLACE_IF_EXISTS | If a context is already set for the transaction pointed to by the *Transaction* parameter, **FltSetTransactionContext** will replace it with the context pointed to by the *NewContext* parameter. Otherwise, it will set the context pointed to by the *NewContext* parameter as the context for the transaction pointed to by the *Transaction* parameter. |
| FLT_SET_CONTEXT_KEEP_IF_EXISTS | If a context is already set for the transaction pointed to by the *Transaction* parameter, **FltSetTransactionContext** will return STATUS_FLT_CONTEXT_ALREADY_DEFINED, and will not replace the existing context or increment the reference count. If a context has not already been set, this routine will set the context pointed to by the *NewContext* parameter as the context for transaction pointed to by the *Transaction* parameter, and will increment the reference count. |

### -param NewContext

[in] Pointer to the new context to be set for the transaction. This parameter is required and cannot be **NULL**.

### -param OldContext

[out, optional] Pointer to a caller-allocated variable that receives the address of the existing transaction context, if one is already set. This parameter is optional and can be **NULL**. For more information about this parameter, see the following Remarks section.

## -returns

**FltSetTransactionContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_CONTEXT_ALREADY_DEFINED | If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for the *Operation* parameter, this error code indicates that a context is already attached to the transaction. Only one context can be attached to a transaction for a given minifilter driver. |
| STATUS_FLT_CONTEXT_ALREADY_LINKED | The context pointed to by the *NewContext* parameter is already linked to an object.  In other words, this error code indicates that *NewContext* is already in use due to a successful prior call of an **FltSet***Xxx***Context** routine. |
| STATUS_FLT_DELETING_OBJECT |
| The instance specified in the *Instance* parameter is being torn down. This is an error code. |
| STATUS_INVALID_PARAMETER | An invalid parameter was passed. For example, the *NewContext* parameter does not point to a valid transaction context, or an invalid value was specified for the *Operation* parameter. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltSetTransactionContext** to attach a context to a transaction or to remove or replace an existing transaction context. A minifilter driver can attach only one context to a given transaction.

### Reference Counting

If **FltSetTransactionContext** succeeds:

- The reference count on *NewContext* is incremented. When *NewContext* is no longer needed, the minifilter must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement its reference count.

Else if **FltSetTransactionContext** fails:

- The reference count on *NewContext* remains unchanged.
- If *OldContext* is not **NULL** and does not point to NULL_CONTEXT then *OldContext* is a referenced pointer to the context currently associated with the transaction. The filter calling **FltSetTransactionContext** must call **FltReleaseContext** for *OldContext* as well when the context pointer is no longer needed.

Regardless of success:

- The filter calling **FltSetTransactionContext** must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement the reference count on the *NewContext* object that was incremented by [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

For more information, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

### Other context operations

For more information, see [Setting Contexts](/windows-hardware/drivers/ifs/setting-contexts), and [Releasing Contexts](/windows-hardware/drivers/ifs/releasing-contexts):

- To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To get a transaction context, call [**FltGetTransactionContext**](nf-fltkernel-fltgettransactioncontext.md).

- To delete a transaction context, call [**FltDeleteTransactionContext**](nf-fltkernel-fltdeletetransactioncontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltCommitComplete**](nf-fltkernel-fltcommitcomplete.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteTransactionContext**](nf-fltkernel-fltdeletetransactioncontext.md)

[**FltEnlistInTransaction**](nf-fltkernel-fltenlistintransaction.md)

[**FltGetTransactionContext**](nf-fltkernel-fltgettransactioncontext.md)

[**FltPrePrepareComplete**](nf-fltkernel-fltprepreparecomplete.md)

[**FltPrepareComplete**](nf-fltkernel-fltpreparecomplete.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltRollbackComplete**](nf-fltkernel-fltrollbackcomplete.md)

[**FltRollbackEnlistment**](nf-fltkernel-fltrollbackenlistment.md)
