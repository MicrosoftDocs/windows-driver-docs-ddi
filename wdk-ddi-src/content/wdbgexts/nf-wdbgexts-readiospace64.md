---
UID: NF:wdbgexts.ReadIoSpace64
title: ReadIoSpace64 function
description: The ReadIoSpace64 function reads from the system I/O locations.
old-location: debugger\readiospace64.htm
tech.root: debugger
ms.assetid: 7578df0d-67ea-4a8c-a89c-6a9d95bff33a
ms.date: 05/03/2018
ms.keywords: ReadIoSpace64, ReadIoSpace64 function [Windows Debugging], WdbgExts_Ref_5e2a7cc2-0dc4-4970-9d6a-c9a2c5130577.xml, debugger.readiospace64, wdbgexts/ReadIoSpace64
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	ReadIoSpace64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadIoSpace64 function


## -description


The <b>ReadIoSpace64</b> function reads from the system I/O locations. 


## -parameters




### -param address

Specifies the I/O address to read from.


### -param data

Specifies the address of a variable to hold the data read. This must be at least the number of bytes contained in <i>size</i>.


### -param size

Specifies the address of a variable that contains the number of bytes to read. <i>Size</i> must be 1, 2, or 4. After the data is read, <i>size</i> will contain the number of bytes actually read.


## -returns



None




## -remarks



If you are writing 32-bit code, you should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553574">ReadIoSpace</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).




