---
UID: NF:wdbgexts.ReadControlSpace
title: ReadControlSpace function (wdbgexts.h)
description: The ReadControlSpace function reads the processor-specific control space into the array pointed to by buf.
old-location: debugger\readcontrolspace.htm
tech.root: debugger
ms.assetid: 4b6955a5-ca03-418d-9eba-fdbe48599922
ms.date: 05/03/2018
keywords: ["ReadControlSpace function"]
ms.keywords: ReadControlSpace, ReadControlSpace function [Windows Debugging], WdbgExts_Ref_8337344a-4a97-4f74-9be4-8fdd771d8bbf.xml, debugger.readcontrolspace, wdbgexts/ReadControlSpace
f1_keywords:
 - "wdbgexts/ReadControlSpace"
 - "ReadControlSpace"
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
- ReadControlSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadControlSpace function


## -description


The <b>ReadControlSpace</b> function reads the processor-specific control space into the array pointed to by <i>buf</i>.


## -parameters




### -param processor

Specifies the number of the processor whose control space is to be read.


### -param address

Specifies the address of the control space.


### -param buf

Specifies the address of an array of bytes to hold the control space data.


### -param size

Specifies the number of bytes in the array pointed to by <i>buf</i>.


## -remarks



If you are writing 64-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readcontrolspace64">ReadControlSpace64</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).




