---
UID: NF:wdbgexts.ReadIoSpaceEx64
title: ReadIoSpaceEx64 function (wdbgexts.h)
description: The ReadIoSpaceEx64 function is an extended version of ReadIoSpace64.
old-location: debugger\readiospaceex64.htm
tech.root: debugger
ms.assetid: 6903a684-e9da-4ff0-b5ea-330b070849c6
ms.date: 05/03/2018
keywords: ["ReadIoSpaceEx64 function"]
ms.keywords: ReadIoSpaceEx64, ReadIoSpaceEx64 function [Windows Debugging], WdbgExts_Ref_5d81517c-f30d-4f8c-b4fe-e3487ad6c49e.xml, debugger.readiospaceex64, wdbgexts/ReadIoSpaceEx64
f1_keywords:
 - "wdbgexts/ReadIoSpaceEx64"
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
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- ReadIoSpaceEx64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadIoSpaceEx64 function


## -description


The <b>ReadIoSpaceEx64</b> function is an extended version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readiospace64">ReadIoSpace64</a>. It reads not only the system I/O locations, but also I/O locations on a bus. <b>ReadIoSpace64</b> works like <b>ReadIoSpaceEx64</b>, except that it defaults <i>interfacetype</i> to ISA, <i>busnumber</i> to zero, and <i>addressspace</i> to 1.


## -parameters




### -param address

Specifies the I/O address to read from.


### -param data

Specifies the address of a variable to hold the data read. This must be at least the number of bytes contained in <i>size</i>.


### -param size

Specifies the address of a variable that contains the number of bytes to read. <i>Size</i> must be 1, 2, or 4. After the data is read, <i>size</i> will contain the number of bytes actually read.


### -param interfacetype

Specifies the type of interface on which the extended I/O space exists. Possible values include ISA, EISA, and MCA. For more information, see ntddk.h, which is available as part of Windows Driver Kit.


### -param busnumber

Specifies the number of the bus on which the extended I/O space exists. This is typically zero, unless there is more than one bus of a given type.


### -param addressspace

This is typically 1.


## -remarks



If you are writing 32-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readiospaceex">ReadIoSpaceEx</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).




