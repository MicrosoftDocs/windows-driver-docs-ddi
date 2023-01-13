---
UID: NS:ntddk._TXN_PARAMETER_BLOCK
title: TXN_PARAMETER_BLOCK (ntddk.h)
description: The TXN_PARAMETER_BLOCK structure contains information about a transacted file operation.
tech.root: ifsk
ms.date: 12/08/2022
keywords: ["TXN_PARAMETER_BLOCK structure"]
ms.keywords: "*PTXN_PARAMETER_BLOCK, PTXN_PARAMETER_BLOCK, PTXN_PARAMETER_BLOCK structure pointer [Installable File System Drivers], TXN_PARAMETER_BLOCK, TXN_PARAMETER_BLOCK structure [Installable File System Drivers], _TXN_PARAMETER_BLOCK, fileinformationstructures_fd9a870c-f8bf-4a9d-8f7c-1dfbdcbab7aa.xml, ifsk.txn_parameter_block, ntddk/PTXN_PARAMETER_BLOCK, ntddk/_TXN_PARAMETER_BLOCK"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: TXN_PARAMETER_BLOCK, *PTXN_PARAMETER_BLOCK
f1_keywords:
 - _TXN_PARAMETER_BLOCK
 - ntddk/_TXN_PARAMETER_BLOCK
 - PTXN_PARAMETER_BLOCK
 - ntddk/PTXN_PARAMETER_BLOCK
 - TXN_PARAMETER_BLOCK
 - ntddk/TXN_PARAMETER_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - _TXN_PARAMETER_BLOCK
 - PTXN_PARAMETER_BLOCK
 - TXN_PARAMETER_BLOCK
---

## -description

The TXN_PARAMETER_BLOCK structure contains information about a transacted file operation.

## -struct-fields

### -field Length

The size, in bytes, of the TXN_PARAMETER_BLOCK structure.

### -field TxFsContext

The miniversion ID for the file.

### -field TransactionObject

An opaque pointer to the transaction object for the transaction.

## -remarks

A *miniversion* is a version of a file that a transacted writer creates during a transaction. (A *transacted writer* is a transacted file handle opened with any permission that is not part of generic read access, but is part of generic write access.)

If a specific miniversion number for the file is not provided, the **TxFsContext** member must be set to TXF_MINIVERSION_DEFAULT_VIEW.

The **TxFsContext** member of the **TXN_PARAMETER_BLOCK** uses TXF_MINIVERSION_DEFAULT_VIEW to get the default view of the requested file that is based on the value of the **TransactionObject** member.  So if **TransactionObject** is the same transaction that has the requested file locked for transacted modification, the caller can see those modifications (the "dirty" view of the file) if the caller can specify the value of the **TransactionObject** member.  If **TransactionObject** is not the same transaction that has the requested file locked for transacted modification, the caller gets a transactionally isolated view of the file if it specifies this value.  

A miniversion exists only as a point-in-time view of a file and has not yet been written as an actual on-disk variant of a given file.  A transacted writer creates a miniversion by using the [FSCTL_TXFS_CREATE_MINIVERSION](/windows/win32/api/winioctl/ni-winioctl-fsctl_txfs_create_miniversion) control code to call [ZwFsControlFile](/previous-versions/ff566462(v=vs.85)).  In response, the system creates a miniversion and returns its miniversion ID.  The transacted writer can continue to make changes to the file thereafter.  If the file is opened later by using the returned miniversion ID as the **TxFsContext** member of the **TXN_PARAMETER_BLOCK** structure, the resulting file handle shows the file as it was at the time that miniversion was created.

All miniversions created in a transaction go away when the transaction ends.  Afterwards, the file can no longer be opened by using the miniversion IDs.

A miniversion is available only to the transacted writer that created the miniversion, not to a transacted reader or non-transacted reader.

The [IoGetTransactionParameterBlock](./nf-ntddk-iogettransactionparameterblock.md) routine returns a pointer to this structure.

## -see-also

[FSCTL_TXFS_CREATE_MINIVERSION](/windows/win32/api/winioctl/ni-winioctl-fsctl_txfs_create_miniversion)

[IoGetTransactionParameterBlock](./nf-ntddk-iogettransactionparameterblock.md)

[ZwFsControlFile](/previous-versions/ff566462(v=vs.85))