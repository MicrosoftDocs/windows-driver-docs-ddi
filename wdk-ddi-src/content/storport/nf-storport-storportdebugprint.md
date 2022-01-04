---
UID: NF:storport.StorPortDebugPrint
title: StorPortDebugPrint function (storport.h)
description: The StorPortDebugPrint routine prints a debug string to the kernel debugger, if the debugger is attached.
old-location: storage\storportdebugprint.htm
tech.root: storage
ms.date: 01/03/2022
keywords: ["StorPortDebugPrint function"]
ms.keywords: StorPortDebugPrint, StorPortDebugPrint routine [Storage Devices], storage.storportdebugprint, storport/StorPortDebugPrint, storprt_4c594dd0-20a0-456f-acdb-3c08198dc8b5.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortDebugPrint
 - storport/StorPortDebugPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortDebugPrint
---

# StorPortDebugPrint function

## -description

The **StorPortDebugPrint** routine prints a debug string to the kernel debugger, if the debugger is attached.

## -parameters

### -param DebugPrintLevel

Contains a value between 0 and 3 that specifies the level of verbosity, where a value of 3 signifies the highest level of verbosity and a value of 0 signifies the lowest level. See Remarks.

### -param DebugMessage

Pointer to the debug message to be printed.

### -param ...

Variadic arguments to be printed with the string that **DebugMessage** points to.

## -returns

None

## -remarks

**StorPortDebugPrint** prints the message pointed to by **DebugMessage**, together with other debugging information depending on the value of **DebugPrintLevel** as follows.

| Value of DebugPrintLevel | Type of information printed |
| ------------------------ | --------------------------- |
| 0                        | Error                       |
| 1                        | Warning                     |
| 2                        | Trace                       |
| 3                        | Informational               |

To see these debug strings, the driver writer must set nt!Kd_STORMINIPORT_Mask. This follows the new system-wide debug print mechanism.

## -see-also

[**DbgPrintEx**](../wdm/nf-wdm-dbgprintex.md)
