---
UID: NF:wdbgexts.ReadIoSpaceEx
title: ReadIoSpaceEx function (wdbgexts.h)
description: The ReadIoSpaceEx function is an extended version of ReadIoSpace.
old-location: debugger\readiospaceex.htm
tech.root: debugger
ms.assetid: de0681e6-c716-4879-8e07-daacc092d18f
ms.date: 05/03/2018
ms.keywords: ReadIoSpaceEx, ReadIoSpaceEx function [Windows Debugging], WdbgExts_Ref_96fa3635-35d1-4d58-835a-96754480170a.xml, debugger.readiospaceex, wdbgexts/ReadIoSpaceEx
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
-	ReadIoSpaceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadIoSpaceEx function


## -description


The <b>ReadIoSpaceEx</b> function is an extended version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553574">ReadIoSpace</a>. It reads not only the system I/O locations, but also I/O locations on a bus. <b>ReadIoSpace</b> works like <b>ReadIoSpaceEx</b>, except that it defaults <i>interfacetype</i> to ISA, <i>busnumber</i> to zero, and <i>addressspace</i> to 1.


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


## -returns



None




## -remarks



If you are writing 64-bit code, you should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553583">ReadIoSpaceEx64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).




