---
UID: NS:dbgeng._DEBUG_READ_USER_MINIDUMP_STREAM
title: "_DEBUG_READ_USER_MINIDUMP_STREAM"
author: windows-driver-content
description: Describes a user minidump to read.
old-location: debugger\debug_read_user_minidump_stream.htm
old-project: debugger
ms.assetid: 07005D52-E851-4AE8-95D8-ED8E26C43DC6
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: "*PDEBUG_READ_USER_MINIDUMP_STREAM, DEBUG_READ_USER_MINIDUMP_STREAM structure [Windows Debugging], DEBUG_READ_USER_MINIDUMP_STREAM, dbgeng/PDEBUG_READ_USER_MINIDUMP_STREAM, dbgeng/DEBUG_READ_USER_MINIDUMP_STREAM, _DEBUG_READ_USER_MINIDUMP_STREAM, debugger.debug_read_user_minidump_stream, PDEBUG_READ_USER_MINIDUMP_STREAM, PDEBUG_READ_USER_MINIDUMP_STREAM structure pointer [Windows Debugging]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	DbgEng.h
apiname:
-	DEBUG_READ_USER_MINIDUMP_STREAM
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_READ_USER_MINIDUMP_STREAM, DEBUG_READ_USER_MINIDUMP_STREAM"
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


The DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM <a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a> operation reads a stream from a user-mode minidump target.
<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>

The DEBUG_READ_USER_MINIDUMP_STREAM structure holds the parameters for the DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM <a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a> operation.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef struct _DEBUG_READ_USER_MINIDUMP_STREAM
{
    IN ULONG  StreamType;
    IN ULONG  Flags;
    IN ULONG64  Offset;
    OUT PVOID  Buffer;
    IN ULONG  BufferSize;
    OUT ULONG  BufferUsed;
} DEBUG_READ_USER_MINIDUMP_STREAM, *PDEBUG_READ_USER_MINIDUMP_STREAM;</pre>
</td>
</tr>
</table></span></div><h3><a id="Members"></a><a id="members"></a><a id="MEMBERS"></a>Members</h3>

The target must be a user-mode minidump file.

Each minidump file contains a number of <i>streams</i>.  These streams are blocks of data written to the minidump file.


