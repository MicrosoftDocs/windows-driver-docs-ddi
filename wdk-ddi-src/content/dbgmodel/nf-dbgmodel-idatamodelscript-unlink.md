---
UID: NF:dbgmodel.IDataModelScript.Unlink
title: IDataModelScript::Unlink (dbgmodel.h)
description: The Unlink method undoes the Execute operation. Any object model manipulations or extensibility points established during the execution of the script are undone.
ms.assetid: 356a8c0b-5ece-4968-9117-fbb146264aa3
ms.date: 08/20/2018
keywords: ["IDataModelScript::Unlink"]
f1_keywords:
 - "dbgmodel/IDataModelScript.Unlink"
ms.keywords: IDataModelScript::Unlink, Unlink, IDataModelScript.Unlink, IDataModelScript::Unlink, IDataModelScript.Unlink
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
- IDataModelScript.Unlink
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScript::Unlink


## -description

The Unlink method undoes the Execute operation. Any object model manipulations or extensibility points established during the execution of the script are undone. After an Unlink operation, the script may be re-executed via a call to Execute or it may be released. 

It is expected that this is called, for instance, upon the closing of a script window by a user interface client.

After the Unlink call, the state of the script should be the same as if the following sequence of operations were performed on a new script: 

- Create a new script

- Populate the new script with the content of the script which was unlinked


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
