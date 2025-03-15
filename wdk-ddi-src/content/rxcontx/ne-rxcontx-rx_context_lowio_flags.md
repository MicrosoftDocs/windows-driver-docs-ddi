---
UID: NE:rxcontx.RX_CONTEXT_LOWIO_FLAGS
tech.root: ifsk
title: RX_CONTEXT_LOWIO_FLAGS
ms.date: 10/30/2024
targetos: Windows
description: Learn more about the RX_CONTEXT_LOWIO_FLAGS enumeration.
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
 - RX_CONTEXT_LOWIO_FLAGS
f1_keywords:
 - RX_CONTEXT_LOWIO_FLAGS
 - rxcontx/RX_CONTEXT_LOWIO_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - RX_CONTEXT_LOWIO_FLAGS
---

## -description

The **RX_CONTEXT_LOWIO_FLAGS** enumeration specifies flags set by RDBSS during low I/O operations.

## -enum-fields

### -field RXCONTEXT_FLAG4LOWIO_PIPE_OPERATION:0x1

The operation is a pipe operation.

### -field RXCONTEXT_FLAG4LOWIO_PIPE_SYNC_OPERATION:0x2

The operation is a synchronous pipe operation.

### -field RXCONTEXT_FLAG4LOWIO_READAHEAD:0x4

Enables read-ahead.

### -field RXCONTEXT_FLAG4LOWIO_THIS_READ_ENLARGED:0x8

This read operation is enlarged.

### -field RXCONTEXT_FLAG4LOWIO_THIS_IO_BUFFERED:0x10

The I/O operation is buffered.

### -field RXCONTEXT_FLAG4LOWIO_LOCK_FCB_RESOURCE_HELD:0x20

The FCB (File Control Block) resource is held.

### -field RXCONTEXT_FLAG4LOWIO_LOCK_WAS_QUEUED_IN_LOCKMANAGER:0x40

The lock was queued in the lock manager.

### -field RXCONTEXT_FLAG4LOWIO_THIS_IO_FAST:0x80

The I/O operation is fast I/O.

### -field RXCONTEXT_FLAG4LOWIO_LOCK_OPERATION_COMPLETED:0x100

The lock operation is completed.

### -field RXCONTEXT_FLAG4LOWIO_LOCK_BUFFERED_ON_ENTRY:0x200

The lock operation is buffered on entry.
