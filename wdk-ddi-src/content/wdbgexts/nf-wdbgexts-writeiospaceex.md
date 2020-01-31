---
UID: NF:wdbgexts.WriteIoSpaceEx
title: WriteIoSpaceEx function (wdbgexts.h)
description: The WriteIoSpaceEx function is an extended version of WriteIoSpace.
old-location: debugger\writeiospaceex.htm
tech.root: debugger
ms.assetid: fb0ae4bb-6d6b-4772-9dbd-ae43f7728313
ms.date: 05/03/2018
ms.keywords: WdbgExts_Ref_53bdc758-08b1-4103-9732-5b7b72c80fdd.xml, WriteIoSpaceEx, WriteIoSpaceEx function [Windows Debugging], debugger.writeiospaceex, wdbgexts/WriteIoSpaceEx
f1_keywords:
 - "wdbgexts/WriteIoSpaceEx"
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
- WriteIoSpaceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WriteIoSpaceEx function


## -description


The <b>WriteIoSpaceEx</b> function is an extended version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writeiospace">WriteIoSpace</a>. It can write to either a system I/O location or an I/O location on a bus. <b>WriteIoSpace</b> works like <b>WriteIoSpaceEx</b>, except that it defaults <i>interfacetype</i> to ISA, <i>busnumber</i> to zero, and <i>addressspace</i> to 1.


## -parameters




### -param address

Specifies the I/O address to write to.


### -param data

Specifies the address of a variable that holds the data to write. This must be at least the number of bytes contained in <i>size</i>.


### -param size

Specifies the address of a variable that contains the number of bytes to write. <i>Size</i> must be 1, 2, or 4. After the data is written, <i>size</i> will contain the number of bytes actually written.


### -param interfacetype

Specifies the type of interface on which the extended I/O space exists. Possible values include ISA, EISA, and MCA. For more information, see ntddk.h, which is available as part of the Windows Driver Kit.


### -param busnumber

Specifies the number of the bus on which the extended I/O space exists. This is typically zero, unless there is more than one bus of a given type.


### -param addressspace

This is typically 1.


## -remarks



If you are writing 64-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writeiospaceex64">WriteIoSpaceEx64</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.



