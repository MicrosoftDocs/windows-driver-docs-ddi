---
UID: NF:dbgeng.IDebugOutputCallbacks2.Output2
title: IDebugOutputCallbacks2::Output2
author: windows-driver-content
description: Returns notifications for the IDebugOutputCallbacks2 interface.
old-location: debugger\idebugoutputcallbacks2_output2.htm
tech.root: debugger
ms.assetid: 2FFF9B54-6E77-4D46-B6C0-5BADD208BFCC
ms.date: 11/13/2018
ms.keywords: DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_EXPLICIT_FLUSH, DEBUG_OUTCBI_TEXT, IDebugOutputCallbacks2 interface [Windows Debugging],Output2 method, IDebugOutputCallbacks2.Output2, IDebugOutputCallbacks2::Output2, Output2, Output2 method [Windows Debugging], Output2 method [Windows Debugging],IDebugOutputCallbacks2 interface, dbgeng/IDebugOutputCallbacks2::Output2, debugger.idebugoutputcallbacks2_output2
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugOutputCallbacks2.Output2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacks2::Output2


## -description


Returns notifications for the <a href="https://msdn.microsoft.com/D35D8960-AD9F-4493-B6CD-3E3049CC3BBD">IDebugOutputCallbacks2</a> interface.


## -parameters




### -param Which [in]

 The kind of notification that is coming in.  

The notifications are defined in the dbgeng.h header using as #defines.

```
#define DEBUG_OUTPUT_NORMAL            0x00000001
// Error output.
#define DEBUG_OUTPUT_ERROR             0x00000002
// Warnings.
#define DEBUG_OUTPUT_WARNING           0x00000004
// Additional output.
#define DEBUG_OUTPUT_VERBOSE           0x00000008
// Prompt output.
#define DEBUG_OUTPUT_PROMPT            0x00000010
// Register dump before prompt.
#define DEBUG_OUTPUT_PROMPT_REGISTERS  0x00000020
// Warnings specific to extension operation.
#define DEBUG_OUTPUT_EXTENSION_WARNING 0x00000040
// Debuggee debug output, such as from OutputDebugString.
#define DEBUG_OUTPUT_DEBUGGEE          0x00000080
// Debuggee-generated prompt, such as from DbgPrompt.
#define DEBUG_OUTPUT_DEBUGGEE_PROMPT   0x00000100
// Symbol messages, such as for !sym noisy.
#define DEBUG_OUTPUT_SYMBOLS           0x00000200
// Output which modifies the status bar
#define DEBUG_OUTPUT_STATUS            0x00000400
// Structured XML status messages
#define DEBUG_OUTPUT_XML               0x00000800

```

For more information, see [DEBUG_OUTPUT_XXX](https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx).


### -param Flags [in]

Flags that are part of the notification payload.


### -param Arg [in]

Arguments that are part of the notification payload.


### -param Text [in, optional]

A pointer to text that is part of the notification payload.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/D35D8960-AD9F-4493-B6CD-3E3049CC3BBD">IDebugOutputCallbacks2</a>
 

 

