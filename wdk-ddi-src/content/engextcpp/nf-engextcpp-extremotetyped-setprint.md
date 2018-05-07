---
UID: NF:engextcpp.ExtRemoteTyped.SetPrint
title: ExtRemoteTyped::SetPrint
author: windows-driver-content
description: The SetPrint method sets the typed data represented by the ExtRemoteTyped object by formatting an expression and then evaluating that expression.
old-location: debugger\extremotetyped_setprint.htm
old-project: debugger
ms.assetid: ae478779-8ec1-4a50-a37c-3017aca2c912
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: EngExtCpp_Ref_5987e1b0-7415-4004-b949-76b3edc02d9a.xml, ExtRemoteTyped interface [Windows Debugging],SetPrint method, ExtRemoteTyped.SetPrint, ExtRemoteTyped::SetPrint, SetPrint, SetPrint method [Windows Debugging], SetPrint method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_setprint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.SetPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::SetPrint


## -description


The <b>SetPrint</b> method sets the typed data represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> object by formatting an expression and then evaluating that expression.


## -parameters




### -param Format [in]

The format string used to create the expression.  This is the same as the format string used by the C <b>printf</b> function.

<div class="alert"><b>Note</b>   While other methods and functions in the debugger engine API provide additional, debugger-specific conversion characters, <b>SetPrint</b> only supports the conversion characters used by <b>printf</b>.</div>
<div> </div>

### -param param






####### - ...

The arguments for the format string, as in <b>printf</b>.  The arguments should match the conversion characters in <i>Format</i>.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>
 

 

