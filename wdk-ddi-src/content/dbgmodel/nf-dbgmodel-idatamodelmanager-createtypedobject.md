---
UID: NF:dbgmodel.IDataModelManager.CreateTypedObject
title: IDataModelManager::CreateTypedObject (dbgmodel.h)
description: The CreateTypedObject method is the method which allows a client to create a representation of a native/language object in the address space of a debug target.
ms.assetid: 6a92ab93-a6fe-4065-a538-ce957349c311
ms.date: 07/17/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateTypedObject, CreateTypedObject, IDataModelManager.CreateTypedObject, IDataModelManager::CreateTypedObject, IDataModelManager.CreateTypedObject
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
-	IDataModelManager.CreateTypedObject
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateTypedObject


## -description

The CreateTypedObject method is the method which allows a client to create a representation of a native/language object in the address space of a debug target. If the type of the newly created object (as indicated by the objectType argument) happens to match one or more type signatures registered with the data model manager as either canonical visualizers or extensions, those matching data models will automatically be attached to the created instance object before it is returned to the caller. 

## -parameters

### -param context
The debug host context in which this object is located. If no explicit context is given, the context of the newly created object will inherit from the context of the objectType argument. A caller can pass the special marker value USE_CURRENT_HOST_CONTEXT to indicate that the object should receive the context which is current in the debugger's user interface.

### -param objectLocation
The location of the object in the address space of the debug target. If the location is a virtual address, the location can be constructed by the client using a 64-bit offset into the address space; otherwise - the location must be retrieved from another debug host interface.

### -param objectType
The type of the object being constructed. The context of the type will propagate to the newly created object if no explicit context is passed in the context argument.

### -param object
The newly created object will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
// As an example, create an instance of nt!_EPROCESS at address 0x100
ComPtr<IDebugHost> spHost;           /* get the host */
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Find a context in which to query.  This queries the current *UI* 
    // context.  You can fetch the context from a process or something 
    // else to query within a specific process.
    ComPtr<IDebugHostModule> spNtModule;
    if (SUCCEEDED(spSym->FindModuleByName(USE_CURRENT_HOST_CONTEXT, 
                                          L"nt", 
                                          &spNtModule)))
    {
        ComPtr<IDebugHostType> spEProcessType;
        if (SUCCEEDED(spNtModule->FindTypeByName(L"_EPROCESS", &spEProcessType)))
        {
            Location creationLocation = 0x100;
            ComPtr<IModelObject> spProcess;
            if (SUCCEEDED(spManager->CreateTypedObject(nullptr, 
                                                       creationLocation,
                                                       spEProcessType.Get(),
                                                       &spProcess)))
            {
                // spProcess is now the _EPROCESS at address 0x100
                // You can get fields, etc... through standard IModelObject methods
            }
        }
    }
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
