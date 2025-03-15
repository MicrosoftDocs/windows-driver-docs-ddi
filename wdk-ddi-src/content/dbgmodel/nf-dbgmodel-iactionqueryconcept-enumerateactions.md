---
UID: NF:dbgmodel.IActionQueryConcept.EnumerateActions
tech.root: debugger
title: IActionQueryConcept::EnumerateActions method (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description: 
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
 - IActionQueryConcept::EnumerateActions
f1_keywords:
 - IActionQueryConcept::EnumerateActions
 - dbgmodel/IActionQueryConcept::EnumerateActions
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateActions
---

## -description

Returns an enumerator to all actions on any object implementing the IActionQueryConcept interface.


## -parameters

### -param contextObject

The pointer to the context object where actions will be enumerated.

### -param actionEnumerator

The pointer to an IActionEnumerator object. This object will point to the first action of the enumeration after the method is called.

## -returns

This method returns a **IActionEnumerator** object that represents the actions on this object.

## -remarks

The returned **IActionEnumerator** object can be used to enumerate all associated actions with the given context object. The enumeration starts on the action which the **actionEnumerator** pointer is set to after the function is called.
## -see-also

[IActionQueryConcept interface](nn-dbgmodel-iactionqueryconcept.md)