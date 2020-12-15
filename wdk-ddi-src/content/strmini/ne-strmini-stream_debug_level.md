---
UID: NE:strmini.__unnamed_enum_0
title: STREAM_DEBUG_LEVEL (strmini.h)
description: The STREAM_DEBUG_LEVEL enumeration lists incrementally increasing levels of debugger output.
old-location: stream\stream_debug_level.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["STREAM_DEBUG_LEVEL enumeration"]
ms.keywords: DebugLevelError, DebugLevelFatal, DebugLevelInfo, DebugLevelMaximum, DebugLevelTrace, DebugLevelVerbose, DebugLevelWarning, STREAM_DEBUG_LEVEL, STREAM_DEBUG_LEVEL enumeration [Streaming Media Devices], ks-struct_9820cc1d-0d8b-43a8-b1a2-bca3f8a23d22.xml, stream.stream_debug_level, strmini/DebugLevelError, strmini/DebugLevelFatal, strmini/DebugLevelInfo, strmini/DebugLevelMaximum, strmini/DebugLevelTrace, strmini/DebugLevelVerbose, strmini/DebugLevelWarning, strmini/STREAM_DEBUG_LEVEL
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
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
req.typenames: STREAM_DEBUG_LEVEL
f1_keywords:
 - STREAM_DEBUG_LEVEL
 - strmini/STREAM_DEBUG_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - strmini.h
api_name:
 - STREAM_DEBUG_LEVEL
---

# STREAM_DEBUG_LEVEL enumeration


## -description

The STREAM_DEBUG_LEVEL enumeration lists incrementally increasing levels of debugger output.

## -enum-fields

### -field DebugLevelFatal

Display only information about nonrecoverable system failure.

### -field DebugLevelError

Display information about serious but recoverable error.

### -field DebugLevelWarning

Display warnings

### -field DebugLevelInfo

Display status information. System must remain responsive.

### -field DebugLevelTrace

Display trace information. System need not remain responsive

### -field DebugLevelVerbose

Display verbose trace information. System need not remain responsive.

### -field DebugLevelMaximum

Display maximum information.

## -see-also

<a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdebugprint">StreamClassDebugPrint</a>
