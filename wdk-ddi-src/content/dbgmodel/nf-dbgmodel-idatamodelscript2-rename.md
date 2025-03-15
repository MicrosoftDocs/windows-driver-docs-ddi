---
UID: NF:dbgmodel.IDataModelScript2.Rename
tech.root: debugger
title: IDataModelScript2::Rename
ms.date: 12/16/2024
targetos: Windows
description: The Rename method assigns a new name to the script.
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
 - IDataModelScript2::Rename
f1_keywords:
 - IDataModelScript2::Rename
 - dbgmodel/IDataModelScript2::Rename
dev_langs:
 - c++
helpviewer_keywords:
 - Rename
---

## -description

The Rename method assigns a new name to the script. It is the responsibility of the script implementation to save this name and return it upon any call to the GetName method. This is often called when a user interface chooses to Save As the script to a new name. Note that renaming the script may affect where the hosting application chooses to project the contents of the script.

## -parameters

### -param scriptName

The name being assigned to the script is passed here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript2 interface](nn-dbgmodel-idatamodelscript2.md)