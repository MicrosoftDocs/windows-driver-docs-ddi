---
UID: NC:wdbgexts.PWINDBG_CHECK_CONTROL_C
title: PWINDBG_CHECK_CONTROL_C
author: windows-driver-content
description: The PWINDBG_CHECK_CONTROL_C (CheckControlC) function checks to see if the user pressed CTRL+C. Use PWINDBG_CHECK_CONTROL_C in all loops to allow the user to press CTRL+C to end long processes.
old-location: debugger\checkcontrolc.htm
old-project: debugger
ms.assetid: 4737870f-3408-4859-9e20-7b69c78f5a3c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CheckControlC, CheckControlC callback function [Windows Debugging], PWINDBG_CHECK_CONTROL_C, WdbgExts_Ref_532229fc-40f0-4226-92af-09ecc5387096.xml, debugger.checkcontrolc, wdbgexts/CheckControlC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdbgexts.h
apiname:
-	CheckControlC
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_CHECK_CONTROL_C callback


## -description


The <b>PWINDBG_CHECK_CONTROL_C</b> (<b>CheckControlC</b>) function checks to see if the user pressed CTRL+C. Use <b>PWINDBG_CHECK_CONTROL_C</b> in all loops to allow the user to press CTRL+C to end long processes.


## -prototype


````
ULONG  CheckControlC(void);
````


## -parameters












## -returns



If the user has pressed CTRL+C, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.




## -remarks



If you are writing a WdbgExts extension, include wdbgexts.h. If you are writing a DbgEng extension that calls this function, include wdbgexts.h before dbgeng.h (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).



