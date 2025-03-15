---
UID: NF:dbgmodel.IDebugHostBaseClass2.IsVirtual
tech.root: debugger
title: IDebugHostBaseClass2::IsVirtual
ms.date: 12/16/2024
targetos: Windows
description: The IsVirtual method determines whether the base class is virtual.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass2::IsVirtual
f1_keywords:
 - IDebugHostBaseClass2::IsVirtual
 - dbgmodel/IDebugHostBaseClass2::IsVirtual
dev_langs:
 - c++
helpviewer_keywords:
 - IsVirtual
---

## -description

The IsVirtual method indicates whether a particular base class is a virtual base class. This distinction is important in the context of class hierarchies, especially when handling virtual inheritance scenarios.

## -parameters

### -param pIsVirtual

A pointer to a boolean that will be set to true if the base class is a virtual base class; otherwise, it will be set to false.

## -returns

## -remarks

If a base class is determined to be virtual, it signifies that the memory location cannot be resolved with a simple offset. In such cases, calling methods like GetOffset may fail, returning an error code of E_NOT_SET, and developers will need to utilize other methods available through the IDebugHostBaseClass2 interface.

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)