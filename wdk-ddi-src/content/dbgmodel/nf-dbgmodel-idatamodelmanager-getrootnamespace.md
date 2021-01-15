---
UID: NF:dbgmodel.IDataModelManager.GetRootNamespace
title: IDataModelManager::GetRootNamespace (dbgmodel.h)
description: The GetRootNamespace method returns the data model's root namespace.
ms.date: 07/19/2018
keywords: ["IDataModelManager::GetRootNamespace"]
ms.keywords: IDataModelManager::GetRootNamespace, GetRootNamespace, IDataModelManager.GetRootNamespace, IDataModelManager::GetRootNamespace, IDataModelManager.GetRootNamespace
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
 - IDataModelManager::GetRootNamespace
 - dbgmodel/IDataModelManager::GetRootNamespace
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager::GetRootNamespace
---

# IDataModelManager::GetRootNamespace


## -description

The GetRootNamespace method returns the data model's root namespace. This is an object which the data model manages and into which the debug host places certain objects. It is expected that at least the following hierarchy is exposed by every host: 

```cpp
• Debugger - represents the debugger which is hosting the data model

    o Sessions - a collection of sessions which represent each debug target 

         Processes -- a collection of processes which represent each process in the debug target 

            - Threads -- a collection of threads which represent each thread within a given process in the debug target
```

## -parameters

### -param rootNamespace

The root namespace of the data model is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IModelObject> spRootNamespace;
if (SUCCEEDED(spManager->GetRootNamespace(&spRootNamespace)))
{
    // We've gotten the root namespace successfully.  Find the Debugger property.
    ComPtr<IModelObject> spDebugger;
    if (SUCCEEDED(spRootNamespace->GetKeyValue(L"Debugger", &spDebugger, nullptr)))
    {
        // We've gotten the "Debugger" property successfully.  Find the 
        // Sessions property.
        ComPtr<IModelObject> spSessions;
        if (SUCCEEDED(spDebugger->GetKeyValue(L"Sessions", &spSessions, nullptr)))
        {
            // We've gotten the "Sessions" property successfully.
        }
    }
}

```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

