---
UID: NF:dbgmodel.IDebugHostModule2.GetBaseLocation
title: IDebugHostModule2::GetBaseLocation
author: windows-driver-content
description: TBD
ms.assetid: e45bc4d7-b8a9-45ff-b366-fad50c82e55a
ms.author: windowsdriverdev
ms.date: 09/18/2018 
ms.topic: method
ms.keywords: IDebugHostModule2::GetBaseLocation, GetBaseLocation, IDebugHostModule2.GetBaseLocation, IDebugHostModule2::GetBaseLocation, IDebugHostModule2.GetBaseLocation
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
-	IDebugHostModule2.GetBaseLocation
product: Windows
targetos: Windows


---

# IDebugHostModule2::GetBaseLocation


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
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
