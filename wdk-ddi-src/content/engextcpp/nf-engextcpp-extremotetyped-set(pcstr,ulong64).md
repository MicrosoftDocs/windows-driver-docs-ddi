---
UID: NF:engextcpp.ExtRemoteTyped.Set(PCSTR,ULONG64)
title: ExtRemoteTyped::Set(PCSTR,ULONG64) (engextcpp.h)
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_pcstr_ulong64.htm
tech.root: debugger
ms.assetid: acf789f7-781d-4078-90cc-79b0d2709696
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging],Set method, ExtRemoteTyped.Set, ExtRemoteTyped.Set(PCSTR,ULONG64), ExtRemoteTyped::Set, ExtRemoteTyped::Set(PCSTR,ULONG64), Set, Set method [Windows Debugging], Set method [Windows Debugging],ExtRemoteTyped class, debugger.extremotetyped_set_pcstr_ulong64
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteTyped.Set
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::Set(PCSTR,ULONG64)


## -description


The <b>Set</b> method sets the typed data represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> object.


## -parameters




### -param Expr [in]

An expression that evaluates to the desired symbol.  This expression is evaluated by the default expression evaluator.


### -param Offset [in]

Specifies an additional parameter that can be used when evaluating the <i>Expr</i> expression.  This additional parameter is available in the expression as the <b>$extin</b> pseudo-register.  For example, to specify a process environment block (PEB) at a particular location, you could set <i>Expr</i> to the C++ expression <code>(ntdll!_PEB *)@$extin</code>. This casts the pseudo-register <b>$extin</b> to a pointer to a PEB. Then, set <i>Offset</i> to the location of the PEB instance.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set (PCSTR)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>



<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set (bool)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544384">ExtRemoteTyped::SetPrint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>
 

 

