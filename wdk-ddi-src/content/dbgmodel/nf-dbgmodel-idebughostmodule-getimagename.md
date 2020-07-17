---
UID: NF:dbgmodel.IDebugHostModule.GetImageName
title: IDebugHostModule::GetImageName (dbgmodel.h)
description: The GetImageName method returns the image name of the module.
ms.assetid: 2671db4c-9fcc-41ba-a08b-15089dd9fe8d
ms.date: 09/18/2018
keywords: ["IDebugHostModule::GetImageName"]
f1_keywords:
 - "dbgmodel/IDebugHostModule.GetImageName"
 - "IDebugHostModule.GetImageName"
ms.keywords: IDebugHostModule::GetImageName, GetImageName, IDebugHostModule.GetImageName, IDebugHostModule::GetImageName, IDebugHostModule.GetImageName
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
- IDebugHostModule.GetImageName
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule::GetImageName


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
ComPtr<IDebugHostModule> spModule; /* get a module (see FindModuleByName) */

BSTR imageName;
if (SUCCEEDED(spModule->GetImageName(false, &imageName)))
{
    // imageName is the name of the image (guaranteed not to have a path 
    // in it).  For instance, this might be "notepad.exe"
    SysFreeString(imageName);
}
```

## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
