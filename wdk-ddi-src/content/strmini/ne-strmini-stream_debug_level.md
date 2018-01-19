---
UID: NE:strmini.STREAM_DEBUG_LEVEL
title: STREAM_DEBUG_LEVEL
author: windows-driver-content
description: The STREAM_DEBUG_LEVEL enumeration lists incrementally increasing levels of debugger output.
old-location: stream\stream_debug_level.htm
old-project: stream
ms.assetid: 42d70c1f-5cce-4097-849d-a5aa05b669b5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: STREAM_DEBUG_LEVEL, STREAM_DEBUG_LEVEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_DEBUG_LEVEL
req.alt-loc: strmini.h
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
req.typenames: STREAM_DEBUG_LEVEL
req.product: Windows 10 or later.
---

# STREAM_DEBUG_LEVEL enumeration



## -description
The STREAM_DEBUG_LEVEL enumeration lists incrementally increasing levels of debugger output.



## -syntax

````
typedef enum  { 
  DebugLevelFatal    = 0,
  DebugLevelError    = 1,
  DebugLevelWarning  = 2,
  DebugLevelInfo     = 3,
  DebugLevelTrace    = 4,
  DebugLevelVerbose  = 5,
  DebugLevelMaximum  = 6
} STREAM_DEBUG_LEVEL;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\strmini\nf-strmini-streamclassdebugprint.md">StreamClassDebugPrint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20STREAM_DEBUG_LEVEL enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

