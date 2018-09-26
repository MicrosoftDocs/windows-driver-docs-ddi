---
UID: NF:dbgmodel.IDataModelManager.Close
title: IDataModelManager::Close
author: windows-driver-content
description: TBD
ms.assetid: 8c20af38-5915-4078-90ef-f6c1156cac1d
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: method
ms.keywords: IDataModelManager::Close, Close, IDataModelManager.Close, IDataModelManager::Close, IDataModelManager.Close
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
-	IDataModelManager.Close
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelManager::Close


## -description

The Close method is called on the data model manager by an application (e.g.: debugger) hosting the data model in order to start the shutdown process of the data model manager. A host of the data model which does not the Close method prior to releasing its final reference on the data model manager may cause undefined behavior including, but not limited to, significant leaks of the management infrastructure for the data model. 

## -parameters


## -returns
This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

if (SUCCEEDED(spManager->Close()))
{
    // We can now shut down the debug host which is hosting the data model.
}

```



## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
