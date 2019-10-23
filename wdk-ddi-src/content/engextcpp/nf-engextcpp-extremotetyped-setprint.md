---
UID: NF:engextcpp.ExtRemoteTyped.SetPrint
title: ExtRemoteTyped::SetPrint (engextcpp.h)
description: The SetPrint method sets the typed data represented by the ExtRemoteTyped object by formatting an expression and then evaluating that expression.
old-location: debugger\extremotetyped_setprint.htm
tech.root: debugger
ms.assetid: ae478779-8ec1-4a50-a37c-3017aca2c912
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_5987e1b0-7415-4004-b949-76b3edc02d9a.xml, ExtRemoteTyped interface [Windows Debugging],SetPrint method, ExtRemoteTyped.SetPrint, ExtRemoteTyped::SetPrint, SetPrint, SetPrint method [Windows Debugging], SetPrint method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_setprint
ms.topic: method
f1_keywords:
 - "engextcpp/ExtRemoteTyped.SetPrint"
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
- ExtRemoteTyped.SetPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::SetPrint


## -description


The <b>SetPrint</b> method sets the typed data represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object by formatting an expression and then evaluating that expression.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>
 

 

