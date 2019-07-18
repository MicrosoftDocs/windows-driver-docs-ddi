---
UID: NF:dbgmodel.IDebugHostModule2.GetVersion
title: IDebugHostModule2::GetVersion (dbgmodel.h)
description: The GetVersion method returns version information about the module (assuming that such information can successfully be read out of the headers).
ms.assetid: a4cfe0b4-ac39-4b19-9f3a-e008075b7923
ms.date: 09/18/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostModule2.GetVersion"
ms.keywords: IDebugHostModule2::GetVersion, GetVersion, IDebugHostModule2.GetVersion, IDebugHostModule2::GetVersion, IDebugHostModule2.GetVersion
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
- IDebugHostModule2.GetVersion
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule2::GetVersion


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
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
