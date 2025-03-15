---
UID: NF:dbgmodel.IDataModelScript2.Unlink
tech.root: debugger
title: IDataModelScript2::Unlink
ms.date: 12/16/2024
targetos: Windows
description: The Unlink method undoes the Execute operation. Any object model manipulations or extensibility points established during the execution of the script are undone.
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
 - IDataModelScript2::Unlink
f1_keywords:
 - IDataModelScript2::Unlink
 - dbgmodel/IDataModelScript2::Unlink
dev_langs:
 - c++
helpviewer_keywords:
 - Unlink
---

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

[IDataModelScript2 interface](nn-dbgmodel-idatamodelscript2.md)