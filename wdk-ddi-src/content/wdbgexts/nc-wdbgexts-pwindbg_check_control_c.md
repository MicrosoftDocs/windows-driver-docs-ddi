---
UID: NC:wdbgexts.PWINDBG_CHECK_CONTROL_C
title: PWINDBG_CHECK_CONTROL_C (wdbgexts.h)
description: The PWINDBG_CHECK_CONTROL_C (CheckControlC) function checks to see if the user pressed CTRL+C. Use PWINDBG_CHECK_CONTROL_C in all loops to allow the user to press CTRL+C to end long processes.
old-location: debugger\checkcontrolc.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PWINDBG_CHECK_CONTROL_C callback function"]
ms.keywords: CheckControlC, CheckControlC callback function [Windows Debugging], PWINDBG_CHECK_CONTROL_C, PWINDBG_CHECK_CONTROL_C callback, WdbgExts_Ref_532229fc-40f0-4226-92af-09ecc5387096.xml, debugger.checkcontrolc, wdbgexts/CheckControlC
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
 - PWINDBG_CHECK_CONTROL_C
 - wdbgexts/PWINDBG_CHECK_CONTROL_C
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - PWINDBG_CHECK_CONTROL_C
---

# PWINDBG_CHECK_CONTROL_C callback function


## -description

The <b>PWINDBG_CHECK_CONTROL_C</b> (<b>CheckControlC</b>) function checks to see if the user pressed CTRL+C. Use <b>PWINDBG_CHECK_CONTROL_C</b> in all loops to allow the user to press CTRL+C to end long processes.

## -parameters

## -returns

If the user has pressed CTRL+C, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## -remarks

If you are writing a WdbgExts extension, include wdbgexts.h. If you are writing a DbgEng extension that calls this function, include wdbgexts.h before dbgeng.h (see <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).

