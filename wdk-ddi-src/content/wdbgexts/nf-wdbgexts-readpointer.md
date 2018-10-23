---
UID: NF:wdbgexts.ReadPointer
title: ReadPointer function
author: windows-driver-content
description: The ReadPointer function reads a pointer from the target.
old-location: debugger\readpointer.htm
tech.root: debugger
ms.assetid: 354b1854-2b3b-4fcf-81cb-fd24595cd9bb
ms.date: 05/03/2018
ms.keywords: ReadPointer, ReadPointer function [Windows Debugging], WdbgExts_Ref_3d78e28a-910f-4b82-a262-28d83d87c6f1.xml, debugger.readpointer, wdbgexts/ReadPointer
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
-	ReadPointer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadPointer function


## -description


The <b>ReadPointer</b> function reads a pointer from the target.


## -parameters




### -param Address

Specifies the address of the pointer to read.


### -param Pointer

Receives the value of the pointer.  If the target uses 32-bit pointers, the pointer is sign-extended to 64 bits.


## -returns



If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.




## -remarks



If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561450">WritePointer</a>
 

 

