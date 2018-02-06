---
UID: NF:wdbgexts.ReadControlSpace
title: ReadControlSpace function
author: windows-driver-content
description: The ReadControlSpace function reads the processor-specific control space into the array pointed to by buf.
old-location: debugger\readcontrolspace.htm
old-project: debugger
ms.assetid: 4b6955a5-ca03-418d-9eba-fdbe48599922
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: wdbgexts/ReadControlSpace, WdbgExts_Ref_8337344a-4a97-4f74-9be4-8fdd771d8bbf.xml, ReadControlSpace function [Windows Debugging], debugger.readcontrolspace, ReadControlSpace
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	ReadControlSpace
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReadControlSpace function


## -description


The <b>ReadControlSpace</b> function reads the processor-specific control space into the array pointed to by <i>buf</i>.


## -syntax


````
__inline VOID ReadControlSpace(
   USHORT processor,
   ULONG  address,
   PVOID  buf,
   ULONG  size
);
````


## -parameters




### -param processor

Specifies the number of the processor whose control space is to be read.


### -param address

Specifies the address of the control space.


### -param buf

Specifies the address of an array of bytes to hold the control space data.


### -param size

Specifies the number of bytes in the array pointed to by <i>buf</i>.


## -returns


None



## -remarks


If you are writing 64-bit code, you should use <a href="..\wdbgexts\ns-wdbgexts-_readcontrolspace64.md">ReadControlSpace64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).



