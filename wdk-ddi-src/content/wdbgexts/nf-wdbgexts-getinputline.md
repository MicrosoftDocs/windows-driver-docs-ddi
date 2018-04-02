---
UID: NF:wdbgexts.GetInputLine
title: GetInputLine function
author: windows-driver-content
description: The GetInputLine function requests an input string from the debugger.
old-location: debugger\getinputline.htm
old-project: debugger
ms.assetid: 18d4aae5-dd11-4c3a-8088-52121f46d208
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetInputLine, GetInputLine function [Windows Debugging], WdbgExts_Ref_ed42718c-5e3e-4fe6-a2d6-f553b6c58800.xml, debugger.getinputline, wdbgexts/GetInputLine
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetInputLine
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetInputLine function


## -description


The <b>GetInputLine</b> function requests an input string from the debugger.


## -parameters




### -param Prompt

Specifies a prompt to indicate what input is being requested.  The prompt is printed to the debugger's output before the input is gathered.  If <i>Prompt</i> is <b>NULL</b>, no prompt is printed.


### -param Buffer

Specifies the buffer to receive the input.


### -param BufferSize

Specifies the size, in characters, of the buffer <i>Buffer</i>.


## -returns



<b>GetInputLine</b> returns the size, in characters, of the input returned to the <i>Buffer</i> buffer, or zero, if no input was returned.



