---
UID: NE:dbgmodel.PointerKind
title: PointerKind (dbgmodel.h)
description: 
ms.assetid: 5601a992-ef28-42ee-99e9-c7e8b2ba08be
ms.date: 07/16/2018
keywords: ["PointerKind enumeration"]
ms.keywords: PointerKind, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - PointerKind
 - dbgmodel/PointerKind
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - PointerKind
---

# PointerKind enumeration


## -description

Defines the kind of a pointer type.

## -enum-fields

### -field PointerStandard

Indicates a standard C/C++ pointer -- a *

### -field PointerReference 

Indicates a C/C++ reference (whether const or not) -- a &

### -field PointerRValueReference 

Indicates a C/C++ rvalue reference (whether const or not) -- a &&

### -field PointerCXHat 

Indicates a C++/CX hat managed pointer (whether const or not) -- a ^

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)