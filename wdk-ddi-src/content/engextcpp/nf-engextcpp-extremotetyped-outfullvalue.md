---
UID: NF:engextcpp.ExtRemoteTyped.OutFullValue
title: ExtRemoteTyped::OutFullValue (engextcpp.h)
description: The OutFullValue method prints the type and value of the typed data represented by this object.
old-location: debugger\extremotetyped_outfullvalue.htm
tech.root: debugger
ms.date: 08/15/2023
keywords: ["ExtRemoteTyped::OutFullValue"]
ms.keywords: EngExtCpp_Ref_30c4c99e-e68e-4f44-b72c-fa67cdcac0fd.xml, ExtRemoteTyped interface [Windows Debugging],OutFullValue method, ExtRemoteTyped.OutFullValue, ExtRemoteTyped::OutFullValue, OutFullValue, OutFullValue method [Windows Debugging], OutFullValue method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_outfullvalue
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
 - ExtRemoteTyped::OutFullValue
 - engextcpp/ExtRemoteTyped::OutFullValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped::OutFullValue
---

# ExtRemoteTyped::OutFullValue

## -description

The <b>OutFullValue</b> method prints the type and value of the typed data represented by this object.

## -remarks

The <b>OutFullValue</b> method prints more detail than the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outsimplevalue">ExtRemoteTyped::OutSimpleValue</a> method. For example, <b>OutFullValue</b> prints dereferenced pointers and the values that they point to.

The type and value information is sent to the debugger engine's output callbacks.

### Returns

This method does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>


<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outsimplevalue">ExtRemoteTyped::OutSimpleValue</a>
