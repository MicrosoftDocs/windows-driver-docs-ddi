---
UID: NC:wdbgexts.PWINDBG_READ_PROCESS_MEMORY_ROUTINE
title: PWINDBG_READ_PROCESS_MEMORY_ROUTINE (wdbgexts.h)
description: The PWINDBG_READ_PROCESS_MEMORY_ROUTINE (ReadMemory) function works like the Win32 ReadProcessMemory function. It reads memory from the process being debugged. The entire area to be read must be accessible, or the operation fails.
old-location: debugger\readmemory.htm
tech.root: debugger
ms.assetid: 36169759-1ee3-4463-a381-67b0277cca25
ms.date: 05/03/2018
keywords: ["PWINDBG_READ_PROCESS_MEMORY_ROUTINE callback function"]
ms.keywords: PWINDBG_READ_PROCESS_MEMORY_ROUTINE, PWINDBG_READ_PROCESS_MEMORY_ROUTINE callback, ReadMemory, ReadMemory callback function [Windows Debugging], WdbgExts_Ref_53e869bc-03c9-4818-80fd-ca1bdafe2b96.xml, debugger.readmemory, wdbgexts/ReadMemory
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PWINDBG_READ_PROCESS_MEMORY_ROUTINE
 - wdbgexts/PWINDBG_READ_PROCESS_MEMORY_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - ReadMemory
---

# PWINDBG_READ_PROCESS_MEMORY_ROUTINE callback function


## -description

The <b>PWINDBG_READ_PROCESS_MEMORY_ROUTINE</b> (<b>ReadMemory</b>) function works like the Win32 <b>ReadProcessMemory</b> function. It reads memory from the process being debugged. The entire area to be read must be accessible, or the operation fails.

## -parameters

### -param offset

Specifies the base address of the memory to be read in the process that is being debugged.

### -param lpBuffer

Points to the buffer to receive the memory read.

### -param cb

Specifies the number of bytes that you want <b>ReadMemory</b> to read.

### -param lpcbBytesRead

Receives the actual number of bytes that <b>ReadMemory</b> transferred into the buffer. This parameter is optional; if it is <b>NULL</b>, it is ignored.

## -returns

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## -remarks

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).