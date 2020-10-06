---
UID: NF:engextcpp.ExtUnknownHolder.operator-assign
title: ExtUnknownHolder::operator= method (engextcpp.h)
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
tech.root: debugger
ms.assetid: 0dd00f33-1ede-43b7-97b7-55942c3f7a27
ms.date: 01/19/2018
keywords: ["ExtUnknownHolder::operator= method"]
ms.keywords: debugger.extremotetyped_operatorequals_debug_typed_data, operator=, ExtCheckedPointer::operator=, ExtDeclBuffer::operator=, ExtRemoteTyped class [Windows Debugging], operator= method, ExtCheckedPointer, ExtDeclAlignedBuffer::operator=, ExtBuffer::operator=, ExtDeleteHolder, ExtBuffer, ExtDeleteHolder::operator=, ExtUnknownHolder, ExtDeclBuffer, ExtUnknownHolder::operator=, operator= method [Windows Debugging], ExtRemoteTyped class, operator= method [Windows Debugging], ExtDeclAlignedBuffer
f1_keywords:
 - "engextcpp/ExtRemoteTyped.operator="
 - "ExtRemoteTyped.operator="
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
req.lib: engextcpp.hpp
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
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtUnknownHolder::operator= method


## -description


The <b>operator=</b> overloaded assignment operator sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.


## -syntax


```
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
```


## -parameters




### -param Unk





#### - Typed [in]

A pointer to a <a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a> structure that describes the data and type to be assigned to this object.


## -returns


<b>operator=</b>  returns the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.



## -remarks


The typed data can also be copied using the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>

<a href="..\engextcpp\nf-engextcpp-extbuffer-operator=.md">ExtRemoteTyped::Operator= (ExtRemoteTyped)</a>

 

 


