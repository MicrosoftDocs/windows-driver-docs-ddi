---
UID: NF:dbgmodel.IActionEnumerator.GetNext
tech.root: debugger
title: IActionEnumerator::GetNext
ms.date: 11/14/2024
targetos: Windows
description: The GetNext method retrieves the next action on the object. This method belongs to the IActionEnumerator interface.
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
 - IActionEnumerator::GetNext
f1_keywords:
 - IActionEnumerator::GetNext
 - dbgmodel/IActionEnumerator::GetNext
dev_langs:
 - c++
helpviewer_keywords:
 - GetNext
---

## -description

Retrieves the next action available for the object that implements the IActionEnumerator interface.

## -parameters

### -param keyName

Pointer which is set to the BSTR of the key name for the next action.

### -param actionName

Pointer which is set to the BSTR of the action's name.

### -param actionDescription

Pointer which is set to the BSTR describing the action.

### -param actionIsDefault

Pointer to boolean value indicating if the retrieved action is the default action.

### -param actionMethod

Pointer to a pointer to IModelObject interface method for the action, optional parameter, may be null if it's not provided.

### -param metadta

Pointer to a pointer to IKeyStore interface for the action's metadata, optional parameter, may be null if it's not provided.

## -returns

If the method succeeds, it returns S_OK. If there are no more actions to enumerate, it returns S_FALSE. Otherwise, it returns an HRESULT error code.

## -remarks

After resolving a single action, the action enumerator is incremented to the next available action. If there are no more actions to enumerate, the method will return S_FALSE.

## -see-also

[IActionEnumerator interface](nn-dbgmodel-iactionenumerator.md)