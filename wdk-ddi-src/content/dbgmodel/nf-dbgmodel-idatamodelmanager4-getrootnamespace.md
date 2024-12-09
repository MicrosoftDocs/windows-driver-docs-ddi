---
UID: NF:dbgmodel.IDataModelManager4.GetRootNamespace
tech.root: debugger
title: IDataModelManager4::GetRootNamespace
ms.date: 12/03/2024
targetos: Windows
description: The GetRootNamespace method returns the data model's root namespace. This is an object which the data model manages and into which the debug host places certain objects.
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
 - IDataModelManager4::GetRootNamespace
f1_keywords:
 - IDataModelManager4::GetRootNamespace
 - dbgmodel/IDataModelManager4::GetRootNamespace
dev_langs:
 - c++
helpviewer_keywords:
 - GetRootNamespace
---

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
ComPtr<IDataModelManager4> spManager; /* get the data model manager */

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

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)