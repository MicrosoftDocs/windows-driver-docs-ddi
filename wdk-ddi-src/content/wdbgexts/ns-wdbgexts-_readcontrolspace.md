---
UID: NS:wdbgexts._READCONTROLSPACE
title: _READCONTROLSPACE (wdbgexts.h)
description: The ReadControlSpace function reads the processor-specific control space into the array pointed to by buf.
old-location: debugger\readcontrolspace.htm
tech.root: debugger
ms.date: 02/27/2018
keywords: ["READCONTROLSPACE structure"]
ms.keywords: "*PREADCONTROLSPACE, READCONTROLSPACE, ReadControlSpace, ReadControlSpace function [Windows Debugging], WdbgExts_Ref_8337344a-4a97-4f74-9be4-8fdd771d8bbf.xml, _READCONTROLSPACE, debugger.readcontrolspace, wdbgexts/ReadControlSpace"
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
req.typenames: READCONTROLSPACE, *PREADCONTROLSPACE
f1_keywords:
 - _READCONTROLSPACE
 - wdbgexts/_READCONTROLSPACE
 - PREADCONTROLSPACE
 - wdbgexts/PREADCONTROLSPACE
 - READCONTROLSPACE
 - wdbgexts/READCONTROLSPACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - ReadControlSpace
---

# _READCONTROLSPACE structure


## -description

The <b>ReadControlSpace</b> function reads the processor-specific control space into the array pointed to by <i>buf</i>.

## -struct-fields

## -remarks

If you are writing 64-bit code, you should use <a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readcontrolspace64">ReadControlSpace64</a> instead. See <a href="/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).
