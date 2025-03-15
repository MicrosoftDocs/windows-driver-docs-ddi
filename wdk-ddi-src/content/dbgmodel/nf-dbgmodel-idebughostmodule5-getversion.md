---
UID: NF:dbgmodel.IDebugHostModule5.GetVersion
tech.root: debugger
title: IDebugHostModule5::GetVersion
ms.date: 02/24/2025
targetos: Windows
description: The GetVersion method, when called on a module, gets module version information from the module headers.
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
 - IDebugHostModule5::GetVersion
f1_keywords:
 - IDebugHostModule5::GetVersion
 - dbgmodel/IDebugHostModule5::GetVersion
dev_langs:
 - c++
helpviewer_keywords:
 - GetVersion
---

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
ComPtr<IDebugHostModule5> spModule; /* get a module (see FindModuleByName) */

ULONG64 fileVersion;
ULONG64 productVersion;
if (SUCCEEDED(spModule->GetVersion(&fileVersion, &productVersion)))
{
    // fileVersion contains a.b.c.d (16.16.16.16) file version
    // productVersion contains a.b.c.d (16.16.16.16) product version
}
```

## -see-also

[IDebugHostModule5 interface](nn-dbgmodel-idebughostmodule5.md)