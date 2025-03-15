---
UID: NE:rxcontx.RX_CONTEXT_FLAGS
tech.root: ifsk
title: RX_CONTEXT_FLAGS
ms.date: 10/29/2024
targetos: Windows
description: Learn more about the RX_CONTEXT_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: rxcontx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rxcontx.h
api_name:
 - RX_CONTEXT_FLAGS
f1_keywords:
 - RX_CONTEXT_FLAGS
 - rxcontx/RX_CONTEXT_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - RX_CONTEXT_FLAGS
---

## -description

The **RX_CONTEXT_FLAGS** enumeration specifies flags set by RDBSS during context creation.

## -enum-fields

### -field RX_CONTEXT_FLAG_FROM_POOL:0x00000001

The context was allocated from pool memory.

### -field RX_CONTEXT_FLAG_WAIT:0x00000002

The operation should wait for completion.

### -field RX_CONTEXT_FLAG_WRITE_THROUGH:0x00000004

The data must actually be transfered to the file before any requested write operation is considered complete.

### -field RX_CONTEXT_FLAG_FLOPPY:0x00000008

The operation involves a floppy disk.

### -field RX_CONTEXT_FLAG_RECURSIVE_CALL:0x00000010

Indicates that the call is a recursive call.

### -field RX_CONTEXT_FLAG_THIS_DEVICE_TOP_LEVEL:0x00000020

Set when the TopLevelIrp field in the thread local storage isn't the current IRP.

### -field RX_CONTEXT_FLAG_DEFERRED_WRITE:0x00000040

The write operation is deferred.

### -field RX_CONTEXT_FLAG_VERIFY_READ:0x00000080

The read operation should be verified.

### -field RX_CONTEXT_FLAG_STACK_IO_CONTEZT:0x00000100

The I/O context is on the stack.

### -field RX_CONTEXT_FLAG_IN_FSP:0x00000200

The operation is being processed by the file system process.

### -field RX_CONTEXT_FLAG_CREATE_MAILSLOT:0x00000400

A mailslot is being created.

### -field RX_CONTEXT_FLAG_MAILSLOT_REPARSE:0x00000800

Indicates a mailslot reparse operation.

### -field RX_CONTEXT_FLAG_ASYNC_OPERATION:0x00001000

The operation is asynchronous.

### -field RX_CONTEXT_FLAG_NO_COMPLETE_FROM_FSP:0x00002000

The operation should not be completed by the file system process.

### -field RX_CONTEXT_FLAG_POST_ON_STABLE_CONDITION:0x00004000

Post the operation only when the condition is stable.

### -field RX_CONTEXT_FLAG_FSP_DELAYED_OVERFLOW_QUEUE:0x00008000

The operation is in the file system process delayed overflow queue.

### -field RX_CONTEXT_FLAG_FSP_CRITICAL_OVERFLOW_QUEUE:0x00010000

The operation is in the file system process critical overflow queue.

### -field RX_CONTEXT_FLAG_MINIRDR_INVOKED:0x00020000

Indicates that the mini-redirector invoked the operation.

### -field RX_CONTEXT_FLAG_WAITING_FOR_RESOURCE:0x00040000

The operation is waiting for a resource.

### -field RX_CONTEXT_FLAG_CANCELLED:0x00080000

The operation was cancelled.

### -field RX_CONTEXT_FLAG_SYNC_EVENT_WAITERS:0x00100000

There are waiters on a synchronous event.

### -field RX_CONTEXT_FLAG_NO_PREPOSTING_NEEDED:0x00200000

No preposting is needed for the operation.

### -field RX_CONTEXT_FLAG_BYPASS_VALIDOP_CHECK:0x00400000

Bypass the valid operation check.

### -field RX_CONTEXT_FLAG_BLOCKED_PIPE_RESUME:0x00800000

A blocked pipe operation is being resumed.

### -field RX_CONTEXT_FLAG_IN_SERIALIZATION_QUEUE:0x01000000

The operation is in the serialization queue.

### -field RX_CONTEXT_FLAG_NO_EXCEPTION_BREAKPOINT:0x02000000

Prevent an exception breakpoint.

### -field RX_CONTEXT_FLAG_NEEDRECONNECT:0x04000000

A reconnect is needed.

### -field RX_CONTEXT_FLAG_MUST_SUCCEED:0x08000000

The operation must succeed.

### -field RX_CONTEXT_FLAG_MUST_SUCCEED_NONBLOCKING:0x10000000

The operation must succeed without blocking.

### -field RX_CONTEXT_FLAG_MUST_SUCCEED_ALLOCATED:0x20000000

Resources must be allocated for the operation to succeed.

### -field RX_CONTEXT_FLAG_MINIRDR_INITIATED:0x80000000

The operation was initiated by the mini-redirector.

## -see-also

[**RX_CONTEXT**](ns-rxcontx-_rx_context.md)

[**RxCreateRxContext**](nf-rxcontx-rxcreaterxcontext.md)
