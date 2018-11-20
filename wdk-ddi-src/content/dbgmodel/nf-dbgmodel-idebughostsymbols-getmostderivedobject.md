---
UID: NF:dbgmodel.IDebugHostSymbols.GetMostDerivedObject
title: IDebugHostSymbols::GetMostDerivedObject
author: windows-driver-content
description: The GetMostDerivedObject will use the type system of the debugger to determine the runtime type of an object from its static type.
ms.assetid: 8fb7a3ae-b941-4332-9699-87b907f33c4a
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::GetMostDerivedObject, GetMostDerivedObject, IDebugHostSymbols.GetMostDerivedObject, IDebugHostSymbols::GetMostDerivedObject, IDebugHostSymbols.GetMostDerivedObject
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
-	IDebugHostSymbols.GetMostDerivedObject
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbols::GetMostDerivedObject


## -description

The GetMostDerivedObject will use the type system of the debugger to determine the runtime type of an object from its static type. This method will only use symbolic information and heuristics available at the type system layer in order to perform this analysis. Such information may include C++ RTTI (run time type information) or analysis of the shape of the virtual function tables of the object. It does not include things such as the preferred runtime type concept on an IModelObject. 

If the analysis cannot find a runtime type or cannot find a runtime type different from the static type passed into the method, the input location and type may be passed out. The method will not fail for these reasons. 


## -parameters

### -param pContext
The context in which the given location is valid. If this value is not specified, the context will be assumed to be identical to the context given by objectType.

### -param location
The location of the statically typed object within the address space given by either the pContext argument or the objectType argument.

### -param objectType
The static type of the object at the given location.

### -param derivedLocation
The location of the runtime typed object within the address space given by either the pContext argument or the objectType argument. This may or may not be the same as the location given by the location argument.
  
### -param derivedType
The runtime type of the object will be returned here. This may or may not be the same as the type passed in the objectType argument.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost;           /* get the host */
ComPtr<IDebugHostType> spStaticType; /* get the static (compile time) type of 
                                     some object (see IModelObject::GetTargetInfo) */
Location staticLocation;             /* get the static location of some object
                                        (see IModelObject::GetTargetInfo) */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    ComPtr<IDebugHostType> spRuntimeType;
    Location runtimeLocation;
    if (SUCCEEDED(spSym->GetMostDerivedObject(USE_CURRENT_HOST_CONTEXT,
                                              spStaticType.Get(), 
                                              staticLocation, 
                                              &spRuntimeType, 
                                              &runtimeLocation)))
    {
        // spRuntimeType contains the runtime type of the object as 
        // determined from type system means (e.g.: RTTI or v-table analysis)
        // runtimeLocation contains the location of the runtime type of the object
    }
}
```



## -see-also
[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
