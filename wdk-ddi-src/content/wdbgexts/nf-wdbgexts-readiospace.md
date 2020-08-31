---
UID: NF:wdbgexts.ReadIoSpace
title: ReadIoSpace function (wdbgexts.h)
description: The ReadIoSpace function reads from the system I/O locations.
old-location: debugger\readiospace.htm
tech.root: debugger
ms.assetid: 31118f7f-fcc4-45f9-a248-a1d6f929f3a2
ms.date: 05/03/2018
keywords: ["ReadIoSpace function"]
ms.keywords: ReadIoSpace, ReadIoSpace function [Windows Debugging], WdbgExts_Ref_e34c76a6-de5d-4347-90a7-959d5392680e.xml, debugger.readiospace, wdbgexts/ReadIoSpace
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
 - ReadIoSpace
 - wdbgexts/ReadIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - ReadIoSpace
---

# ReadIoSpace function


## -description

The <b>ReadIoSpace</b> function reads from the system I/O locations.

## -parameters

### -param address

Specifies the I/O address to read from.

### -param data

Specifies the address of a variable to hold the data read. This must be at least the number of bytes contained in <i>size</i>.

### -param size

Specifies the address of a variable that contains the number of bytes to read (1, 2, or 4 only). After the data is read, <i>size</i> will contain the number of bytes actually read.

## -remarks

If you are writing 64-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readiospace64">ReadIoSpace64</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).

