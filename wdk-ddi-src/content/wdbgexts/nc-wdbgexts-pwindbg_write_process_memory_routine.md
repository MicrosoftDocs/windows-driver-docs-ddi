---
UID: NC:wdbgexts.PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE
title: PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE (wdbgexts.h)
description: The PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE (WriteMemory) function works like the Win32 WriteProcessMemory routine. It writes memory to the process being debugged. The entire area to be written must be accessible, or the operation fails.
old-location: debugger\writememory.htm
tech.root: debugger
ms.assetid: 9e734d5d-736b-48cb-9635-f27006dd00e0
ms.date: 05/03/2018
keywords: ["PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE callback function"]
ms.keywords: PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE, PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE callback, WdbgExts_Ref_72933b84-f8ce-432e-b89c-09c2668aa90e.xml, WriteMemory, WriteMemory callback function [Windows Debugging], debugger.writememory, wdbgexts/WriteMemory
f1_keywords:
 - "wdbgexts/WriteMemory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdbgexts.h
api_name:
- WriteMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE callback function


## -description


The <b>PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE</b> (<b>WriteMemory</b>) function works like the Win32 <b>WriteProcessMemory</b> routine. It writes memory to the process being debugged. The entire area to be written must be accessible, or the operation fails. 


## -parameters




### -param offset

Specifies the base address of the memory to be written in the process that is being debugged.


### -param lpBuffer


### -param cb

Specifies the number of bytes that <b>WriteMemory</b> should write.


### -param lpcbBytesWritten

Receives the actual number of bytes that <b>WriteMemory</b> transferred from the buffer. This parameter is optional; if it is <b>NULL</b>, it is ignored.


#### - lpbuffer

Points to the buffer that contains the data to be written.


## -returns



If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.




## -remarks



For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.



