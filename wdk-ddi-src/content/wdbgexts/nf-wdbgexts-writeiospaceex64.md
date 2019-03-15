---
UID: NF:wdbgexts.WriteIoSpaceEx64
title: WriteIoSpaceEx64 function (wdbgexts.h)
description: The WriteIoSpaceEx64 function is an extended version of WriteIoSpace64.
old-location: debugger\writeiospaceex64.htm
tech.root: debugger
ms.assetid: 4fc874ab-b31d-41ae-baeb-18819c4e3970
ms.date: 05/03/2018
ms.keywords: WdbgExts_Ref_378f5c2e-fcbc-4401-8527-f6e98bfa6257.xml, WriteIoSpaceEx64, WriteIoSpaceEx64 function [Windows Debugging], debugger.writeiospaceex64, wdbgexts/WriteIoSpaceEx64
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- WriteIoSpaceEx64
product:
- Windows
targetos: Windows
req.typenames: 
---

# WriteIoSpaceEx64 function


## -description


The <b>WriteIoSpaceEx64</b> function is an extended version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561408">WriteIoSpace64</a>. It can write to either a system I/O location or an I/O location on a bus. <b>WriteIoSpace64</b> works like <b>WriteIoSpaceEx64</b>, except that it defaults <i>interfacetype</i> to ISA, <i>busnumber</i> to zero, and <i>addressspace</i> to 1.


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


## -returns



None




## -remarks



If you are writing 32-bit code, you should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561413">WriteIoSpaceEx</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.



