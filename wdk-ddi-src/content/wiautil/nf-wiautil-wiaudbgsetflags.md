---
UID: NF:wiautil.wiauDbgSetFlags
title: wiauDbgSetFlags macro (wiautil.h)
description: The wiauDbgSetFlags function sets debugging flags.
old-location: image\wiaudbgsetflags.htm
tech.root: image
ms.assetid: e3b944ef-daa5-412c-ac11-7b08d2b9333b
ms.date: 05/03/2018
keywords: ["wiauDbgSetFlags macro"]
ms.keywords: image.wiaudbgsetflags, wiauDbgSetFlags, wiauDbgSetFlags function [Imaging Devices], wiauFncs_d0f9a6a3-6958-44cb-9467-7f6413f95ca7.xml, wiautil/wiauDbgSetFlags
f1_keywords:
 - "wiautil/wiauDbgSetFlags"
 - "wiauDbgSetFlags"
req.header: wiautil.h
req.include-header: Wiautil.h
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
- wiautil.h
api_name:
- wiauDbgSetFlags
targetos: Windows
req.typenames: 
---

# wiauDbgSetFlags macro

## -description

The **wiauDbgSetFlags** function sets debugging flags.

## -parameters

### -param a

- **flags** - A set of flags that control message logging. This parameter can be set to a combination of the following values:

    | Value | Description |
    | --- | --- |
    | WIAUDBG_BREAK_ON_ERRORS | Call **DebugBreak** when an error occurs. |
    | WIAUDBG_DONT_LOG | Do not log to either log file or debugger. |
    | WIAUDBG_DONT_LOG_TO_DEBUGGER | Do not log to debugger. |
    | WIAUDBG_DONT_LOG_TO_FILE | Do not log to log file. |
    | WIAUDBG_DUMP | Log data. |
    | WIAUDBG_ERRORS | Log error messages. |
    | WIAUDBG_FNS | Log function entries and exits. |
    | WIAUDBG_PRINT_INFO | Log thread, file, and line number. |
    | WIAUDBG_PRINT_TIME | Log current time. |
    | WIAUDBG_TRACES | Log trace messages. |
    | WIAUDBG_WARNINGS | Log warning messages. |

## -see-also

[wiauDbgFlags](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgflags)
