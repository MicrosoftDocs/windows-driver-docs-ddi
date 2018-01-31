---
UID: NF:wdbgexts.GetInputLine
title: GetInputLine function
author: windows-driver-content
description: The GetInputLine function requests an input string from the debugger.
old-location: debugger\getinputline.htm
old-project: debugger
ms.assetid: 18d4aae5-dd11-4c3a-8088-52121f46d208
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: WdbgExts_Ref_ed42718c-5e3e-4fe6-a2d6-f553b6c58800.xml, wdbgexts/GetInputLine, GetInputLine function [Windows Debugging], GetInputLine, debugger.getinputline
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	GetInputLine
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetInputLine function


## -description


The <b>GetInputLine</b> function requests an input string from the debugger.


## -syntax


````
__inline ULONG GetInputLine(
   PCSTR Prompt,
   PSTR  Buffer,
   ULONG BufferSize
);
````


## -parameters




#### - Prompt

Specifies a prompt to indicate what input is being requested.  The prompt is printed to the debugger's output before the input is gathered.  If <i>Prompt</i> is <b>NULL</b>, no prompt is printed.


#### - Buffer

Specifies the buffer to receive the input.


#### - BufferSize

Specifies the size, in characters, of the buffer <i>Buffer</i>.


## -returns


<b>GetInputLine</b> returns the size, in characters, of the input returned to the <i>Buffer</i> buffer, or zero, if no input was returned.


