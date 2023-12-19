---
UID: NF:engextcpp.ExtDeclAlignedBuffer.operator-assign(_T)
title: "ExtDeclAlignedBuffer::operator= method (engextcpp.h)"
description: "The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object."
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
tech.root: debugger
ms.date: 12/19/2023
keywords: ["ExtDeclAlignedBuffer::operator= method"]
ms.keywords: debugger.extremotetyped_operatorequals_debug_typed_data, operator=, ExtCheckedPointer::operator=, ExtRemoteTyped class [Windows Debugging], operator= method, ExtCheckedPointer, ExtDeclAlignedBuffer::operator=, ExtBuffer::operator=, ExtBuffer, operator= method [Windows Debugging], ExtRemoteTyped class, operator= method [Windows Debugging], ExtDeclAlignedBuffer
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

# ExtDeclAlignedBuffer::operator= method


## -description


The <b>operator=</b> overloaded assignment operator sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.


## -syntax


```
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
```


## -parameters




### -param Ptr





### -param Typed [in]

A pointer to a <a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a> structure that describes the data and type to be assigned to this object.


## -returns


<b>operator=</b>  returns the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.



## -remarks


The typed data can also be copied using the [ExtBuffer::Copy method](nf-engextcpp-extbuffer-copy(const_t_ulong).md)



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>

<a href="..\engextcpp\nf-engextcpp-extbuffer-operator-assign(extbuffer__t__).md">ExtRemoteTyped::Operator= (ExtRemoteTyped)</a>
