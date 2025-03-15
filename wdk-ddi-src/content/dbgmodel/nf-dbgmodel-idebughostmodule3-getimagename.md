---
UID: NF:dbgmodel.IDebugHostModule3.GetImageName
tech.root: debugger
title: IDebugHostModule3::GetImageName
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule3::GetImageName method gets the image name or full path of the module as an allocated string.
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
 - IDebugHostModule3::GetImageName
f1_keywords:
 - IDebugHostModule3::GetImageName
 - dbgmodel/IDebugHostModule3::GetImageName
dev_langs:
 - c++
helpviewer_keywords:
 - GetImageName
---

## -description

The GetImageName method returns the image name of the module. Depending on the value of the allowPath argument, the returned image name may or may not include the full path to the image.

## -parameters

### -param allowPath

If true, indicates that the full path to the module may be included in the output. Whether such path is or is not included is up to the specific debug host and the manner in which the module was loaded. If false, indicates that only the image name of the module will be included in the output.

### -param imageName

The image name (or full path) of the module will be returned here as an allocated string. The caller is responsible for calling SysFreeString to free the string after use.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule3> spModule; /* get a module (see FindModuleByName) */

BSTR imageName;
if (SUCCEEDED(spModule->GetImageName(false, &imageName)))
{
    // imageName is the name of the image (guaranteed not to have a path 
    // in it).  For instance, this might be "notepad.exe"
    SysFreeString(imageName);
}
```

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)