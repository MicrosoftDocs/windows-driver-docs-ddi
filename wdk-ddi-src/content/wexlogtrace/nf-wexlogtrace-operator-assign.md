---
UID: NF:wexlogtrace.operator-assign
title: operator= function (wexlogtrace.h)
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
tech.root: debugger
ms.assetid: 0dd00f33-1ede-43b7-97b7-55942c3f7a27
ms.date: 08/10/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging], operator= method, debugger.extremotetyped_operatorequals_debug_typed_data, operator=, operator= method [Windows Debugging], operator= method [Windows Debugging], ExtRemoteTyped class
ms.topic: function
f1_keywords:
 - "wexlogtrace/ExtRemoteTyped.operator="
req.header: wexlogtrace.h
req.include-header: Engextcpp.hpp, Wexlogtrace.h, Wextestclass.h, Wextestclass.h
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
req.lib: NtosKrnl.exe
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- arrayofelements.hpp
api_name:
- ExtRemoteTyped.operator=
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# operator= function


## -description

The <b>operator=</b> overloaded assignment operator sets the typed data represented by the [ExtRemoteTyped](../engextcpp/nl-engextcpp-extremotetyped.md) object by copying the information from another object.

## -syntax


```
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
```


## -parameters

#### - Typed [in]

A pointer to a [ExtRemoteTyped](../engextcpp/nl-engextcpp-extremotetyped.md) structure that describes the data and type to be assigned to this object.


## -returns

<b>operator=</b>  returns the [ExtRemoteTyped](../engextcpp/nl-engextcpp-extremotetyped.md) object.


## -remarks

The typed data can also be copied using the [ExtBuffer::Copy method](../engextcpp/nf-engextcpp-extbuffer-copy.md) method.


## -see-also

[ExtRemoteTyped](../engextcpp/nl-engextcpp-extremotetyped.md)


[DEBUG_TYPED_DATA](../wdbgexts/ns-wdbgexts-_debug_typed_data.md)



 

 


