---
UID: NF:dbgmodel.IConstructableConcept.CreateInstance
tech.root: debugger
title: IConstructableConcept::CreateInstance  method (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description: The CreateInstance method creates an instance of an object that implements the IConstructableConcept interface.
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
 - IConstructableConcept::CreateInstance
f1_keywords:
 - IConstructableConcept::CreateInstance
 - dbgmodel/IConstructableConcept::CreateInstance
dev_langs:
 - c++
helpviewer_keywords:
 - CreateInstance
---

## -description

Creates an instance of the object or model implementing the IConstructableConcept interface.


## -parameters

### -param argCount

The count of arguments to be passed to the constructor of the object.

### -param ppArguments

Pointer to the array of arguments passed to the constructor of the object. The array should have at least 'argCount' elements.

### -param ppInstance

Pointer to a location where a pointer to the newly created instance will be written.

## -returns

If the method succeeds, it returns S_OK, and a pointer to the newly created instance is written to 'ppInstance'. Otherwise, it returns an HRESULT error code.

## -see-also

[IConstructableConcept interface](nn-dbgmodel-iconstructableconcept.md)