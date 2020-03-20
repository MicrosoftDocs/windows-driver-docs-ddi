---
UID: NC:wdbgexts.PWINDBG_DISASM
title: PWINDBG_DISASM (wdbgexts.h)
description: The PWINDBG_DISASM (Disasm) function disassembles the instruction pointed to by lpOffset and places the printable string into lpBuffer.
old-location: debugger\disasm.htm
tech.root: debugger
ms.assetid: 1a986b7b-b45b-4546-a14e-4abb76ddf764
ms.date: 05/03/2018
keywords: ["PWINDBG_DISASM callback function"]
ms.keywords: Disasm, Disasm callback function [Windows Debugging], PWINDBG_DISASM, PWINDBG_DISASM callback, WdbgExts_Ref_787ab353-1829-4111-8931-2192bfb9cd0c.xml, debugger.disasm, wdbgexts/Disasm
f1_keywords:
 - "wdbgexts/Disasm"
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
- UserDefined
api_location:
- wdbgexts.h
api_name:
- Disasm
product:
- Windows
targetos: Windows
req.typenames: 
---

# PWINDBG_DISASM callback function


## -description


The <b>PWINDBG_DISASM</b> (<b>Disasm</b>) function disassembles the instruction pointed to by <i>lpOffset</i> and places the printable string into <i>lpBuffer</i>.


## -parameters




### -param *lpOffset

Points to the instruction to be disassembled.


### -param lpBuffer

Receives the disassembled instruction.


### -param fShowEffectiveAddress

Specifies whether or not to print the effective address.


## -returns



If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.



