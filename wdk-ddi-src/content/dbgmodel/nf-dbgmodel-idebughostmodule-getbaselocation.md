---
UID: NF:dbgmodel.IDebugHostModule.GetBaseLocation
title: IDebugHostModule::GetBaseLocation
description: The GetBaseLocation method returns the base load address of the module as a location structure.
ms.assetid: b0e14eb7-c8bc-4a20-bbea-692d837cdcd7
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostModule::GetBaseLocation, GetBaseLocation, IDebugHostModule.GetBaseLocation, IDebugHostModule::GetBaseLocation, IDebugHostModule.GetBaseLocation
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostModule.GetBaseLocation
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule::GetBaseLocation


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
ComPtr<IDebugHostModule> spModule; /* get a module (see FindModuleByName) */

Location moduleBase;
if (SUCCEEDED(spModule->GetBaseLocation(&moduleBase)))
{
    // moduleBase contains the base address of the module
}
```

## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
