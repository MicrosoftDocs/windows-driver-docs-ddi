---
UID: NF:dbgmodel.IHostDataModelAccess.GetDataModel
title: IHostDataModelAccess::GetDataModel (dbgmodel.h)
description: The GetDataModel method is the method on the bridge interface which provides access to both sides of the data model.
ms.assetid: f1763b5e-b8e6-47d9-a8f9-12f564744769
ms.date: 07/20/2018
f1_keywords:
 - "dbgmodel/IHostDataModelAccess.GetDataModel"
ms.keywords: IHostDataModelAccess::GetDataModel, GetDataModel, IHostDataModelAccess.GetDataModel, IHostDataModelAccess::GetDataModel, IHostDataModelAccess.GetDataModel
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
- IHostDataModelAccess.GetDataModel
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IHostDataModelAccess::GetDataModel

## -description

The GetDataModel method is the method on the bridge interface which provides access to both sides of the data model:

• The debug host (the lower edge of the debugger) is expressed by the returned [IDebugHost](nn-dbgmodel-idebughost.md) interface

• The data model's main component -- the data model manager is expressed by the returned [IDataModelManager](nn-dbgmodel-idatamodelmanager.md) interface


## -parameters

### -param manager
An interface to the data model manager is returned here.

### -param host
The core interface of the debug host is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugClient> spClient; /* get an IDebugClient* from DbgEng */

ComPtr<IHostDataModelAccess> spDataModelAccess;
if (SUCCEEDED(spClient.As(&spDataModelAccess)))
{
    ComPtr<IDataModelManager> spManager;
    ComPtr<IDebugHost> spHost;
    if (SUCCEEDED(spDataModelAccess->GetDataModel(&spManager, &spHost)))
    {
        // The data model manager and debug host have been fetched from the engine interface.
    }
}
```

## -see-also

[IDataHostModelAccess interface](nn-dbgmodel-ihostdatamodelaccess.md)
