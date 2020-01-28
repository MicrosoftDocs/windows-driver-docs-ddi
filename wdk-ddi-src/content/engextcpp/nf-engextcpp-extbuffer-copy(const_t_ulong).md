---
UID: NF:engextcpp.ExtBuffer.Copy(const _T,ULONG)
title: ExtBuffer::Copy method (engextcpp.h)
description: The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_copy_debug_typed_data.htm
tech.root: debugger
ms.assetid: bfeafa09-49b7-45b3-84d8-afad5f43b78e
ms.date: 01/19/2018
ms.keywords: Copy method [Windows Debugging], Copy, ExtBuffer, Copy method [Windows Debugging], ExtRemoteTyped class, ExtBuffer::Copy, debugger.extremotetyped_copy_debug_typed_data, ExtRemoteTyped class [Windows Debugging], Copy method
f1_keywords:
 - "engextcpp/ExtRemoteTyped.Copy"
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
- engextcpp.hpp
api_name:
- ExtRemoteTyped.Copy
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtBuffer::Copy method


## -description


The <b>Copy</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.


## -syntax


```cpp
void Copy(
  [in] const DEBUG_TYPED_DATA *Typed
);
```


## -parameters




### -param Src




### -param Elts





#### - Typed [in]

The typed data description to copy. This becomes the typed data represented by this object.


## -returns


This method does not return a value.



## -remarks


The typed data can also be copied using the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy ExtRemoteTyped</a> method.



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff544357(v=vs.85)">ExtRemoteTyped::operator=</a>

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>

 

 


