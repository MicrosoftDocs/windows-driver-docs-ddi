---
UID: NF:engextcpp.ExtRemoteTyped.operator-assign
title: ExtRemoteTyped::operator= method (engextcpp.h)
description: The ExtRemoteTyped class provides the ability to manipulate typed data on the target.
old-location: debugger\extremotetyped.htm
tech.root: debugger
ms.assetid: 1f5d71a5-fa60-4819-9838-2b035ef21374
ms.date: 08/09/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging], described, ExtRemoteTyped::Copy, Copy, ErtIoctl, EngExtCpp_Ref_04970dac-e759-4a04-a1e0-8dab752c1418.xml, operator=, ExtRemoteTyped, ExtRemoteTyped::GetSimpleValue, ExtRemoteTyped::operator=, engextcpp/ExtRemoteTyped, debugger.extremotetyped, ExtRemoteTyped class [Windows Debugging], Clear, GetSimpleValue, ExtRemoteTyped::ErtIoctl, ExtRemoteTyped::Clear
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Windows
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
- ExtRemoteTyped
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::operator= method

## -description

The *operator=* method is part of the <b>ExtRemoteTyped</b> class. The <b>ExtRemoteTyped</b> class provides the ability to manipulate typed data on the target.  An instance of this class represents a small region of memory on the target. This region is interpreted as a specific type.  This class provides methods for manipulating the memory according to the type and for accessing the object hierarchy on the target.

<b>ExtRemoteTyped</b> is a subclass of <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>.


## -parameters


## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>

 

 


