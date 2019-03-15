---
UID: NF:dbgmodel.IDataModelScript.Rename
title: IDataModelScript::Rename (dbgmodel.h)
description: The Rename method assigns a new name to the script. 
ms.assetid: b6bb9297-1c8a-4f4c-a5c7-dfa62408be9d
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScript::Rename, Rename, IDataModelScript.Rename, IDataModelScript::Rename, IDataModelScript.Rename
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
- IDataModelScript.Rename
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScript::Rename


## -description

The Rename method assigns a new name to the script. It is the responsibility of the script implementation to save this name and return it upon any call to the GetName method. This is often called when a user interface chooses to Save As the script to a new name. Note that renaming the script may affect where the hosting application chooses to project the contents of the script. 

## -parameters

### -param scriptName

The name being assigned to the script is passed here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
