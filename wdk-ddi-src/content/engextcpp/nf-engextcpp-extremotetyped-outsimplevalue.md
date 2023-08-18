---
UID: NF:engextcpp.ExtRemoteTyped.OutSimpleValue
title: ExtRemoteTyped::OutSimpleValue (engextcpp.h)
description: The OutSimpleValue method prints the value of the typed data represented by this object.
old-location: debugger\extremotetyped_outsimplevalue.htm
tech.root: debugger
ms.date: 08/11/2023
keywords: ["ExtRemoteTyped::OutSimpleValue"]
ms.keywords: EngExtCpp_Ref_8592b96c-7253-42f9-a704-739e539bad66.xml, ExtRemoteTyped interface [Windows Debugging],OutSimpleValue method, ExtRemoteTyped.OutSimpleValue, ExtRemoteTyped::OutSimpleValue, OutSimpleValue, OutSimpleValue method [Windows Debugging], OutSimpleValue method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_outsimplevalue
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
 - ExtRemoteTyped::OutSimpleValue
 - engextcpp/ExtRemoteTyped::OutSimpleValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped::OutSimpleValue
---

# ExtRemoteTyped::OutSimpleValue

## -description

The <b>OutSimpleValue</b> method prints the value of the typed data represented by this object.

## -remarks

The <b>OutSimpleValue</b> method does not print as much detail as the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outfullvalue">ExtRemoteTyped::OutFullValue</a> method.

The value is sent to the debugger engine's output callbacks.

### Returns

This method does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outfullvalue">ExtRemoteTyped::OutFullValue</a>
