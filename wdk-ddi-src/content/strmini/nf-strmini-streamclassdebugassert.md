---
UID: NF:strmini.StreamClassDebugAssert
title: StreamClassDebugAssert function (strmini.h)
description: A minidriver can use the StreamClassDebugAssert routine in a checked build environment to fail an assert, causing the stream class driver to output a debug message and break into the kernel debugger.
old-location: stream\streamclassdebugassert.htm
tech.root: stream
ms.assetid: df9b3231-4c43-4d4b-b128-e8d6a9f21b17
ms.date: 04/23/2018
ms.keywords: StreamClassDebugAssert, StreamClassDebugAssert routine [Streaming Media Devices], strclass-routines_6f9302e6-592f-4097-830c-83b05a54d335.xml, stream.streamclassdebugassert, strmini/StreamClassDebugAssert
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Stream.lib
-	Stream.dll
api_name:
-	StreamClassDebugAssert
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassDebugAssert function


## -description


A minidriver can use the <b>StreamClassDebugAssert</b> routine in a checked build environment to fail an assert, causing the stream class driver to output a debug message and break into the kernel debugger.


## -parameters




### -param File [in]

Pointer to a <b>NULL</b>-terminated string containing the file name in which the assert occurred.


### -param Line [in]

Specifies the line number of the assert.


### -param AssertText [in]

Pointer to a <b>NULL</b>-terminated string containing text to be printed in the debug message.


### -param AssertValue [in]

Specifies a value to be printed in the debug message.


## -returns



None




## -remarks



When running a checked version of the class driver, asserts are recognized, and result in a debug message and breakpoint. When running a free version of the class driver, asserts are ignored. For more information, see <a href="https://msdn.microsoft.com/544b922b-58e4-4cbb-a76c-d8e13ae17e55">Stream Class Debugging</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543626">DbgBreakPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568235">StreamClassDebugPrint</a>
 

 

