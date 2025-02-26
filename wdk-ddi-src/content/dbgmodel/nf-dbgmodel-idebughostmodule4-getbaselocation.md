---
UID: NF:dbgmodel.IDebugHostModule4.GetBaseLocation
tech.root: debugger
title: IDebugHostModule4::GetBaseLocation
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule4::GetBaseLocation method, when called on a module, gets the base loading address of the module as a location structure.
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
 - IDebugHostModule4::GetBaseLocation
f1_keywords:
 - IDebugHostModule4::GetBaseLocation
 - dbgmodel/IDebugHostModule4::GetBaseLocation
dev_langs:
 - c++
helpviewer_keywords:
 - GetBaseLocation
---

## -description

The GetBaseLocation method returns the base load address of the module as a location structure. The returned location structure for a module will typically refer to a virtual address.

## -parameters

### -param moduleBaseLocation

The loading address of the base of the module in memory is returned here as a location structure. Typically, this refers to a virtual address.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule4> spModule; /* get a module (see FindModuleByName) */

Location moduleBase;
if (SUCCEEDED(spModule->GetBaseLocation(&moduleBase)))
{
    // moduleBase contains the base address of the module
}
```

## -see-also

[IDebugHostModule4 interface](nn-dbgmodel-idebughostmodule4.md)