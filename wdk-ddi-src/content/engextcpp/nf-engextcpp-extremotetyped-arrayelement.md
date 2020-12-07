---
UID: NF:engextcpp.ExtRemoteTyped.ArrayElement
title: ExtRemoteTyped::ArrayElement (engextcpp.h)
description: The ArrayElement method returns the typed data in the specified array element of the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_arrayelement.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::ArrayElement"]
ms.keywords: ArrayElement, ArrayElement method [Windows Debugging], ArrayElement method [Windows Debugging],ExtRemoteTyped interface, EngExtCpp_Ref_086fc0ab-cf63-4079-86d4-552dd2a1593d.xml, ExtRemoteTyped interface [Windows Debugging],ArrayElement method, ExtRemoteTyped.ArrayElement, ExtRemoteTyped::ArrayElement, debugger.extremotetyped_arrayelement
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
 - ExtRemoteTyped::ArrayElement
 - engextcpp/ExtRemoteTyped::ArrayElement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped.ArrayElement
---

# ExtRemoteTyped::ArrayElement


## -description

The <b>ArrayElement</b> method returns the typed data in the specified array element of the typed data represented by the <b>ExtRemoteTyped</b> object.

## -parameters

### -param Index 

[in]
The index of the array element.

## -returns

<b>ArrayElement</b> returns a new <b>ExtRemoteData</b> object that represents the typed data for the specified element of the array.

## -remarks

If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="/previous-versions/windows/hardware/previsioning-framework/ff544357(v=vs.85)">ExtRemoteTyped::operator[]</a> overloaded operator performs a similar function.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff544357(v=vs.85)">ExtRemoteTyped::operator[]</a>
