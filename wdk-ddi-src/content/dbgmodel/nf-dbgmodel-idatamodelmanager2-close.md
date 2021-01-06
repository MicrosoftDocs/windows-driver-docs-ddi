---
UID: NF:dbgmodel.IDataModelManager2.Close
title: IDataModelManager2::Close (dbgmodel.h)
description: The Close method is called on the data model manager by an application (debugger) hosting the data model in order to start the shutdown process of the data model manager.
ms.date: 07/20/2018
keywords: ["IDataModelManager2::Close"]
ms.keywords: IDataModelManager2::Close, Close, IDataModelManager2.Close, IDataModelManager2::Close, IDataModelManager2.Close
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelManager2::Close
 - dbgmodel/IDataModelManager2::Close
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager2.Close
---

# IDataModelManager2::Close


## -description

The Close method is called on the data model manager by an application (e.g.: debugger) hosting the data model in order to start the shutdown process of the data model manager. A host of the data model which does not the Close method prior to releasing its final reference on the data model manager may cause undefined behavior including, but not limited to, significant leaks of the management infrastructure for the data model.

## -returns

This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager2> spManager2; /* get the data model manager */

if (SUCCEEDED(spManager->Close()))
{
    // We can now shut down the debug host which is hosting the data model.
}

```

## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)

