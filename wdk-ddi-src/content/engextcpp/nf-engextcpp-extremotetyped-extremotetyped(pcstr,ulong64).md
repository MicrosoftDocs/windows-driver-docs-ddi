---
UID: NF:engextcpp.ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64)
title: ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64)
author: windows-driver-content
description: The ExtRemoteTyped constructor creates a new instance of the ExtRemoteTyped class.
old-location: debugger\extremotetyped_extremotetyped_pcstr_ulong64.htm
tech.root: debugger
ms.assetid: 85b6e625-ad5a-4e11-a39a-418e0aa152c3
ms.date: 5/3/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging],ExtRemoteTyped constructor, ExtRemoteTyped constructor [Windows Debugging], ExtRemoteTyped constructor [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped.ExtRemoteTyped, ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64), ExtRemoteTyped::ExtRemoteTyped, ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64), debugger.extremotetyped_extremotetyped_pcstr_ulong64
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
-	ExtRemoteTyped.ExtRemoteTyped
product:
-	Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64)


## -description


The <b>ExtRemoteTyped</b> constructor creates a new instance of the <b>ExtRemoteTyped</b> class.


## -parameters




### -param Expr [in]

An expression that evaluates to the desired symbol.  This expression is evaluated by the default expression evaluator.


### -param Offset [in]

An additional parameter that can be used when evaluating the <i>Expr</i> expression.  This additional parameter is available in the expression as the <b>$extin</b> pseudo-register.  For example, to specify a process environment block (PEB) at a particular location, you could set <i>Expr</i> to the C++ expression <code>(ntdll!_PEB *)@$extin</code>. This casts the pseudo-register <b>$extin</b> to a pointer to a PEB. Then, set <i>Offset</i> to the location of the PEB structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544242">ExtRemoteTyped::ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/6cfe4258-be66-49fd-b154-124951ed0dd1">ExtRemoteTyped::ExtRemoteTyped (DEBUG_TYPED_DATA)</a>



<a href="https://msdn.microsoft.com/8a5ee124-d5ce-431d-9f7f-ff7894f0c28c">ExtRemoteTyped::ExtRemoteTyped (ExtRemoteTyped)</a>



<a href="https://msdn.microsoft.com/fbf10d5c-0a79-49f2-87e9-af63614e625c">ExtRemoteTyped::ExtRemoteTyped (PCSTR)</a>



<a href="https://msdn.microsoft.com/824f47da-2a56-4e09-b23a-a9754c1e2063">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64, bool)</a>



<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>
 

 

