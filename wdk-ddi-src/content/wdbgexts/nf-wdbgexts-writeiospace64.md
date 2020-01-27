---
UID: NF:wdbgexts.WriteIoSpace64
title: WriteIoSpace64 function (wdbgexts.h)
description: The WriteIoSpace64 function writes to the system I/O locations.
old-location: debugger\writeiospace64.htm
tech.root: debugger
ms.assetid: c750d3de-8481-42d5-a290-00e49d5fe82b
ms.date: 05/03/2018
ms.keywords: WdbgExts_Ref_81d45454-9dd4-46f1-823b-1a2345890106.xml, WriteIoSpace64, WriteIoSpace64 function [Windows Debugging], debugger.writeiospace64, wdbgexts/WriteIoSpace64
f1_keywords:
 - "wdbgexts/WriteIoSpace64"
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
- WriteIoSpace64
product:
- Windows
targetos: Windows
req.typenames: 
---

# WriteIoSpace64 function


## -description


The <b>WriteIoSpace64</b> function writes to the system I/O locations. 


## -parameters




### -param address

Specifies the I/O address to write to.


### -param data

Specifies the address of a variable that holds the data to write. This must be at least the number of bytes contained in <i>size</i>.


### -param size

Specifies the address of a variable that contains the number of bytes to write. <i>Size</i> must be 1, 2, or 4. After the data is written, <i>size</i> will contain the number of bytes actually written.


## -remarks



If you are writing 32-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writeiospace">WriteIoSpace</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.



