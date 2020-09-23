---
UID: NF:wdbgexts.WritePointer
title: WritePointer function (wdbgexts.h)
description: The WritePointer function writes a pointer to the target.
old-location: debugger\writepointer.htm
tech.root: debugger
ms.assetid: 5f3d6cd6-e138-4114-8fac-03cbe1c7aa68
ms.date: 05/03/2018
keywords: ["WritePointer function"]
ms.keywords: WdbgExts_Ref_ab18dbae-3a69-43a1-97dd-d0711e4db54e.xml, WritePointer, WritePointer function [Windows Debugging], debugger.writepointer, wdbgexts/WritePointer
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WritePointer
 - wdbgexts/WritePointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - WritePointer
---

# WritePointer function


## -description

The <b>WritePointer</b> function writes a pointer to the target.

## -parameters

### -param Address

Specifies the address to write the pointer to.

### -param Pointer

Specifies the value of the pointer.  If the target uses 32-bit pointers, <i>Pointer</i> is a 32-bit value that has been sign-extended to 64-bits.

## -returns

If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## -remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readpointer">ReadPointer</a>