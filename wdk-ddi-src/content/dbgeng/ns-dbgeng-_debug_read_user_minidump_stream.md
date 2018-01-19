---
UID: NS:dbgeng._DEBUG_READ_USER_MINIDUMP_STREAM
title: _DEBUG_READ_USER_MINIDUMP_STREAM
author: windows-driver-content
description: Describes a user minidump to read.
old-location: debugger\debug_read_user_minidump_stream.htm
old-project: debugger
ms.assetid: 07005D52-E851-4AE8-95D8-ED8E26C43DC6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_READ_USER_MINIDUMP_STREAM, DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_READ_USER_MINIDUMP_STREAM
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM
---

# _DEBUG_READ_USER_MINIDUMP_STREAM structure



## -description
Describes a user minidump to read.



## -syntax

````
typedef struct _DEBUG_READ_USER_MINIDUMP_STREAM {
  ULONG   StreamType;
  ULONG   Flags;
  ULONG64 Offset;
  PVOID   Buffer;
  ULONG   BufferSize;
  ULONG   BufferUsed;
} DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM;
````


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
The DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM <a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a> operation reads a stream from a user-mode minidump target.</p>