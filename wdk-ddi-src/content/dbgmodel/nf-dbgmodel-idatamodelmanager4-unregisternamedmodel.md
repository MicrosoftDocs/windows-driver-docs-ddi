---
UID: NF:dbgmodel.IDataModelManager4.UnregisterNamedModel
tech.root: debugger
title: IDataModelManager4::UnregisterNamedModel
ms.date: 12/03/2024
targetos: Windows
description: The UnregisterNamedModel method undoes a prior call to the RegisterNamedModel method.
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
 - IDataModelManager4::UnregisterNamedModel
f1_keywords:
 - IDataModelManager4::UnregisterNamedModel
 - dbgmodel/IDataModelManager4::UnregisterNamedModel
dev_langs:
 - c++
helpviewer_keywords:
 - UnregisterNamedModel
---

## -description

The UnregisterNamedModel method undoes a prior call to RegisterNamedModel. It removes the association between a data model and a name under which it can be looked up.

## -parameters

### -param modelName

The name which will be unregistered. Any data model registered under this name will no longer be registered.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager;    /* get the data model manager */

if (SUCCEEDED(spManager->UnregisterNamedModel(
    L"Debugger.Models.Process.PrivateProcessExtension")))
{
    // Whatever data model was registered under
    // Debugger.Models.Process.PrivateProcessExtension is no longer registered.
}
```

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)