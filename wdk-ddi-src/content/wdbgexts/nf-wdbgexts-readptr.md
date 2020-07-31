---
UID: NF:wdbgexts.ReadPtr
title: ReadPtr function (wdbgexts.h)
description: The ReadPtr function reads a pointer from the target. ReadPointer should be used instead of this function as the return value of ReadPointer is more consistent with the rest of the WdbgExts API.
old-location: debugger\readptr.htm
tech.root: debugger
ms.assetid: e3999ecc-9884-4ae6-8e01-be4538b1d53a
ms.date: 05/03/2018
keywords: ["ReadPtr function"]
ms.keywords: ReadPtr, ReadPtr function [Windows Debugging], WdbgExts_Ref_4eaec659-6522-4d7f-b64a-ad771f93eb56.xml, debugger.readptr, wdbgexts/ReadPtr
f1_keywords:
 - "wdbgexts/ReadPtr"
 - "ReadPtr"
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
- ReadPtr
targetos: Windows
req.typenames: 
---

# ReadPtr function


## -description


The <b>ReadPtr</b> function reads a pointer from the target.  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readpointer">ReadPointer</a> should be used instead of this function as the return value of <b>ReadPointer</b> is more consistent with the rest of the WdbgExts API.


## -parameters




### -param Addr

Specifies the address of the pointer to read.


### -param pPointer

Receives the value of the pointer.  If the target uses 32-bit pointers, the pointer is sign-extended to 64 bits.


## -returns



If the function succeeds, the return value is <b>FALSE</b>; otherwise, it is <b>TRUE</b>.




## -remarks



This function is identical to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readpointer">ReadPointer</a>, except the meaning of the return value is reversed.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readpointer">ReadPointer</a>
 

 

