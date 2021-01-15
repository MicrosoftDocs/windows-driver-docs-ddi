---
UID: NF:engextcpp.ExtDeleteHolder.Set
title: ExtDeleteHolder::Set method (engextcpp.h)
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_bool.htm
tech.root: debugger
ms.date: 01/19/2018
keywords: ["ExtDeleteHolder::Set method"]
ms.keywords: Set method [Windows Debugging], Set, ExtBuffer::Set, ExtCheckedPointer, ExtDeleteHolder, ExtRemoteTyped class [Windows Debugging], Set method, ExtCheckedPointer::Set, ExtBuffer, debugger.extremotetyped_set_bool, ExtDeleteHolder::Set, Set method [Windows Debugging], ExtRemoteTyped class
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
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
f1_keywords:
 - ExtDeleteHolder::Set
 - engextcpp/ExtDeleteHolder::Set
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtDeleteHolder::Set
---

# ExtDeleteHolder::Set method


## -description

The <b>Set</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.

## -parameters

### -param Ptr

#### - PtrTo [in]

Specifies whether or not to set the <b>ExtRemoteTyped</b> instance to the specified typed data, or to a pointer to the specified typed data.  If <i>PtrTo</i> is <code>true</code>, the <b>ExtRemoteTyped</b> instance will be a pointer to the typed data.


#### - TypeModBase [in]

The base address of the module to which the type belongs.


#### - TypeId [in]

The type ID of the type.


#### - Offset [in]

Specifies the location of the data in the target's memory.

## -syntax

```cpp
void Set(
  [in] bool    PtrTo,
  [in] ULONG64 TypeModBase,
  [in] ULONG   TypeId,
  [in] ULONG64 Offset
);
```

## -see-also

<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR)</a>

<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList</a>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-setprint">ExtRemoteTyped::SetPrint</a>

<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>

<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>

<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>

