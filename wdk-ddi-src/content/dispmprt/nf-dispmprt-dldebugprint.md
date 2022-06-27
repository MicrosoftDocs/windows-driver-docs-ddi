---
UID: NF:dispmprt.DlDebugPrint
title: DlDebugPrint function
description: Prints the specified debug message to the kernel debugger.
tech.root: display
ms.date: 05/31/2022
keywords: ["DlDebugPrint function"]
ms.keywords: DlDebugPrint
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlDebugPrint
 - dispmprt/DlDebugPrint
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlDebugPrint
product:
 - Windows
dev_langs:
 - c++
---

# DlDebugPrint function

## -description

Prints the specified debug message to the kernel debugger.

## -parameters

### -param DebugPrintLevel

Specifies the level of debug messages to be printed.

### -param DebugMessage

Pointer to a string containing the debug message to be printed.

### -param ...

Additional parameters.
