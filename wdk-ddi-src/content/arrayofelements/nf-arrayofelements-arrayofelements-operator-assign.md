---
UID: NF:arrayofelements.ArrayOfElements.operator-assign
title: operator= function (arrayofelements.h)
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
tech.root: debugger
ms.date: 07/22/2022
keywords: ["operator= function"]
ms.keywords: ExtRemoteTyped class [Windows Debugging], operator= method, debugger.extremotetyped_operatorequals_debug_typed_data, operator=, operator= method [Windows Debugging], operator= method [Windows Debugging], ExtRemoteTyped class
req.header: arrayofelements.hpp
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
targetos: Windows
req.typenames: SDEV_SECURE_ACPI_INFO_ENTRY, *PSDEV_SECURE_ACPI_INFO_ENTRY
f1_keywords:
 - ArrayOfElements::operator=
 - arrayofelements/ArrayOfElements::operator=
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - arrayofelements.hpp
api_name:
 - ArrayOfElements::operator=
---

# operator= function

## -description

The **operator=** overloaded assignment operator sets the typed data represented by the [ExtRemoteTyped](..\engextcpp\nl-engextcpp-extremotetyped.md) object by copying the information from another object.

## -parameters

## -param unnamedParam1

A pointer to a **[DEBUG_TYPED_DATA](/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data)** structure that describes the data and type to be assigned to this object.

## -returns

**operator=**  returns the [ExtRemoteTyped](..\engextcpp\nl-engextcpp-extremotetyped.md) object.

## -syntax

```cpp
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
```

## -remarks

The typed data can also be copied using the [ExtRemoteTyped::Copy(Debug Typed Data)](..\engextcpp\nf-engextcpp-extbuffer-copy.md) or [ExtRemoteTyped::Copy(ExtRemoteTyped)](..\engextcpp\nf-engextcpp-extbuffer-copy.md) methods.

## -see-also

- [ExtRemoteTyped](..\engextcpp\nl-engextcpp-extremotetyped.md)
- [ExtRemoteTyped::Operator= (ExtRemoteTyped)](..\wextestclass\nf-wextestclass-fixtureinvokefunctor-operator=.md)
- [DEBUG_TYPED_DATA](..\wdbgexts\ns-wdbgexts-_debug_typed_data.md)
