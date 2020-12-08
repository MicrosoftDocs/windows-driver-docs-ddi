---
UID: NF:storport.StorPortDebugPrint
title: StorPortDebugPrint function (storport.h)
description: The StorPortDebugPrint routine prints a debug string to the kernel debugger, if the debugger is attached.
old-location: storage\storportdebugprint.htm
tech.root: storage
ms.date: 03/29/2018
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

The <b>StorPortDebugPrint</b> routine prints a debug string to the kernel debugger, if the debugger is attached.

## -parameters

### -param DebugPrintLevel

Indicates the amount of debug information that will be displayed.

### -param DebugMessage

Pointer to the debug message to be printed.

### -param param

TBD

## -returns

None

## -remarks

To see these debug strings, the driver writer must set nt!Kd_STORMINIPORT_Mask. This follows the new system-wide debug print mechanism.

