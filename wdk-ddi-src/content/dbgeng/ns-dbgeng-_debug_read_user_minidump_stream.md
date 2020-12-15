---
UID: NS:dbgeng._DEBUG_READ_USER_MINIDUMP_STREAM
title: _DEBUG_READ_USER_MINIDUMP_STREAM (dbgeng.h)
description: Describes a user minidump to read.
old-location: debugger\debug_read_user_minidump_stream.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_READ_USER_MINIDUMP_STREAM structure"]
ms.keywords: "*PDEBUG_READ_USER_MINIDUMP_STREAM, DEBUG_READ_USER_MINIDUMP_STREAM, DEBUG_READ_USER_MINIDUMP_STREAM structure [Windows Debugging], PDEBUG_READ_USER_MINIDUMP_STREAM, PDEBUG_READ_USER_MINIDUMP_STREAM structure pointer [Windows Debugging], _DEBUG_READ_USER_MINIDUMP_STREAM, dbgeng/DEBUG_READ_USER_MINIDUMP_STREAM, dbgeng/PDEBUG_READ_USER_MINIDUMP_STREAM, debugger.debug_read_user_minidump_stream"
req.header: dbgeng.h
req.include-header: DbgEng.h
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
req.typenames: DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM
f1_keywords:
 - _DEBUG_READ_USER_MINIDUMP_STREAM
 - dbgeng/_DEBUG_READ_USER_MINIDUMP_STREAM
 - PDEBUG_READ_USER_MINIDUMP_STREAM
 - dbgeng/PDEBUG_READ_USER_MINIDUMP_STREAM
 - DEBUG_READ_USER_MINIDUMP_STREAM
 - dbgeng/DEBUG_READ_USER_MINIDUMP_STREAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - DEBUG_READ_USER_MINIDUMP_STREAM
---

# _DEBUG_READ_USER_MINIDUMP_STREAM structure


## -description

Describes a user minidump to read.

## -struct-fields

### -field StreamType

The type of stream.

### -field Flags

Flags.

### -field Offset

The offset of stream.

### -field Buffer

Specifies the beginning of the buffer to read.

### -field BufferSize

Specifies the length of the buffer to read.

### -field BufferUsed

The buffer used value.

## -remarks

The DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a> operation reads a stream from a user-mode minidump target.

<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


The DEBUG_READ_USER_MINIDUMP_STREAM structure holds the parameters for the DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a> operation.


```cpp
typedef struct _DEBUG_READ_USER_MINIDUMP_STREAM
{
    IN ULONG  StreamType;
    IN ULONG  Flags;
    IN ULONG64  Offset;
    OUT PVOID  Buffer;
    IN ULONG  BufferSize;
    OUT ULONG  BufferUsed;
} DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM;
```

<h3><a id="Members"></a><a id="members"></a><a id="MEMBERS"></a>Members</h3>


The target must be a user-mode minidump file.

Each minidump file contains a number of <i>streams</i>.  These streams are blocks of data written to the minidump file.
