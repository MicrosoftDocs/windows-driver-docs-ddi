---
UID: NF:engextcpp.ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64)
title: ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64) (engextcpp.h)
description: The ExtRemoteTyped constructor creates a new instance of the ExtRemoteTyped class.
old-location: debugger\extremotetyped_extremotetyped_pcstr_ulong64.htm
tech.root: debugger
ms.assetid: 85b6e625-ad5a-4e11-a39a-418e0aa152c3
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64)"]
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging],ExtRemoteTyped constructor, ExtRemoteTyped constructor [Windows Debugging], ExtRemoteTyped constructor [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped.ExtRemoteTyped, ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64), ExtRemoteTyped::ExtRemoteTyped, ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64), debugger.extremotetyped_extremotetyped_pcstr_ulong64
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - ExtRemoteTyped::ExtRemoteTyped
 - engextcpp/ExtRemoteTyped::ExtRemoteTyped
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped.ExtRemoteTyped
---

# ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64)


## -description

The <b>ExtRemoteTyped</b> constructor creates a new instance of the <b>ExtRemoteTyped</b> class.

## -parameters

### -param Expr 

[in]
An expression that evaluates to the desired symbol.  This expression is evaluated by the default expression evaluator.

### -param Offset 

[in]
An additional parameter that can be used when evaluating the <i>Expr</i> expression.  This additional parameter is available in the expression as the <b>$extin</b> pseudo-register.  For example, to specify a process environment block (PEB) at a particular location, you could set <i>Expr</i> to the C++ expression <code>(ntdll!_PEB *)@$extin</code>. This casts the pseudo-register <b>$extin</b> to a pointer to a PEB. Then, set <i>Offset</i> to the location of the PEB structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped">ExtRemoteTyped::ExtRemoteTyped</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(constdebug_typed_data)">ExtRemoteTyped::ExtRemoteTyped (DEBUG_TYPED_DATA)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(constextremotetyped_)">ExtRemoteTyped::ExtRemoteTyped (ExtRemoteTyped)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr)">ExtRemoteTyped::ExtRemoteTyped (PCSTR)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64, bool)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList</a>