---
UID: NF:engextcpp.ExtRemoteTyped.operator-assign(constExtRemoteTyped&)
title: ExtRemoteTyped::operator=(const ExtRemoteTyped &) (engextcpp.h)
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_extremotetyped.htm
tech.root: debugger
ms.assetid: c6ca8078-a331-4952-9854-831ba95404ee
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::operator=(const ExtRemoteTyped &)"]
ms.keywords: ExtRemoteTyped class [Windows Debugging],operator= method, ExtRemoteTyped.operator=, ExtRemoteTyped.operator=(const ExtRemoteTyped &), ExtRemoteTyped.operator=(const ExtRemoteTyped&), ExtRemoteTyped::operator=, ExtRemoteTyped::operator=(const ExtRemoteTyped &), debugger.extremotetyped_operatorequals_extremotetyped, operator=, operator= method [Windows Debugging], operator= method [Windows Debugging],ExtRemoteTyped class
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
f1_keywords:
 - ExtRemoteTyped::operator=
 - engextcpp/ExtRemoteTyped::operator=
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped.operator=
---

# ExtRemoteTyped::operator=(const ExtRemoteTyped &)


## -description

The <b>operator=</b> overloaded assignment operator sets the typed data represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object by copying the information from another object.

## -parameters

### -param Typed 

[in, ref]
An existing <a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object that represents the data and type to be assigned to this object.

## -returns

<b>operator=</b>  returns the <a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object.

## -remarks

The typed data can also be copied using the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-copy(constdebug_typed_data)">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-copy(constextremotetyped_)">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff544342(v=vs.85)">ExtRemoteTyped::Operator= (DEBUG_TYPED_DATA)</a>