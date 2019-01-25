---
UID: NF:wdbgexts.WriteIoSpace
title: WriteIoSpace function (wdbgexts.h)
description: The WriteIoSpace function writes to the system I/O locations.
old-location: debugger\writeiospace.htm
tech.root: debugger
ms.assetid: 4d1a3df6-2440-46b7-8e73-f017f5fcfa51
ms.date: 05/03/2018
ms.keywords: WdbgExts_Ref_1aa4429d-9d99-4c7c-8870-7a75ccaad6e5.xml, WriteIoSpace, WriteIoSpace function [Windows Debugging], debugger.writeiospace, wdbgexts/WriteIoSpace
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
-	WriteIoSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# WriteIoSpace function


## -description


The <b>WriteIoSpace</b> function writes to the system I/O locations. 


## -parameters




### -param address

Specifies the I/O address to write to.


### -param data

Specifies the address of a variable that holds the data to write. This must be at least the number of bytes contained in <i>size</i>.


### -param size

Specifies the address of a variable that contains the number of bytes to write. <i>Size</i> must be 1, 2, or 4. After the data is written, <i>size</i> will contain the number of bytes actually written.


## -returns



None




## -remarks



If you are writing 64-bit code, you should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561408">WriteIoSpace64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.



