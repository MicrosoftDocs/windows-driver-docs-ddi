---
UID: NF:minitape.TapeDebugPrint
title: TapeDebugPrint function (minitape.h)
description: The TapeDebugPrint routine prints the indicated string.
old-location: storage\tapedebugprint.htm
tech.root: storage
ms.date: 01/03/2022
keywords: ["TapeDebugPrint function"]
ms.keywords: TapeDebugPrint, TapeDebugPrint routine [Storage Devices], minitape/TapeDebugPrint, storage.tapedebugprint, tapeclas_cc0c28ed-17e9-40cf-bf04-e906aa4f74f0.xml
req.header: minitape.h
req.include-header: Minitape.h
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
req.lib: Tape.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - TapeDebugPrint
 - minitape/TapeDebugPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Tape.lib
 - Tape.dll
api_name:
 - TapeDebugPrint
---

# TapeDebugPrint function

## -description

The **TapeDebugPrint** routine prints the indicated string.

## -parameters

### -param DebugPrintLevel

Determines whether the string is printed. If **DebugPrintLevel** is less than or equal to the tape class global variable **TapeClassDebug**, **TapeDebugPrint** prints the debug message, otherwise nothing is printed. If this parameter has a value of zero, **TapeClassDebug** always prints the message.

### -param DebugMessage

Pointer to the string to be printed.

### -param ...

Variadic arguments for the string that **DebugMessage** points to.

## -returns

None
