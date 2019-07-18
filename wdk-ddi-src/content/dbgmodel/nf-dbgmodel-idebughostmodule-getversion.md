---
UID: NF:dbgmodel.IDebugHostModule.GetVersion
title: IDebugHostModule::GetVersion (dbgmodel.h)
description: The GetVersion method returns version information about the module (assuming that such information can successfully be read out of the headers). 
ms.assetid: e7874502-d3ef-42a4-a7cc-6bba4a341403
ms.date: 09/18/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostModule.GetVersion"
ms.keywords: IDebugHostModule::GetVersion, GetVersion, IDebugHostModule.GetVersion, IDebugHostModule::GetVersion, IDebugHostModule.GetVersion
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostModule.GetVersion
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule::GetVersion


## -description

The GetVersion method returns version information about the module (assuming that such information can successfully be read out of the headers). If a given version is requested (via a non-nullptr output pointer) and it cannot be read, an appropriate error code will be returned from the method call. 

## -parameters

### -param fileVersion
If a non-nullptr address is supplied, the file version of the module will be returned here. If the file version cannot be read from the module headers, this method will fail if a non-nullptr address is provided here. If the file version cannot be read from the module headers and this value is provided as nullptr, it will not cause a failure.

### -param productVersion
If a non-nullptr address is supplied, the product version of the module as indicated in the module headers is returned here. If the product version cannot be read from the module headers, this method will fail if a non-nullptr address is provided here. If the product version cannot be read from the module headers and this value is provided as nullptr, it will not cause a failure.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule> spModule; /* get a module (see FindModuleByName) */

ULONG64 fileVersion;
ULONG64 productVersion;
if (SUCCEEDED(spModule->GetVersion(&fileVersion, &productVersion)))
{
    // fileVersion contains a.b.c.d (16.16.16.16) file version
    // productVersion contains a.b.c.d (16.16.16.16) product version
}
```

## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
