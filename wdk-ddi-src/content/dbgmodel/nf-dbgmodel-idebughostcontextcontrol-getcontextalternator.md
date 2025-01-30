---
UID: NF:dbgmodel.IDebugHostContextControl.GetContextAlternator
tech.root: debugger
title: IDebugHostContextControl::GetContextAlternator
ms.date: 01/15/2025
targetos: Windows
description: The GetContextAlternator method retrieves context alternator, which allows a temporary context change/switch.
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
 - IDebugHostContextControl::GetContextAlternator
f1_keywords:
 - IDebugHostContextControl::GetContextAlternator
 - dbgmodel/IDebugHostContextControl::GetContextAlternator
dev_langs:
 - c++
helpviewer_keywords:
 - GetContextAlternator
---

## -description

It retrieves a context alternator, allowing a temporary context change or switch.

## -parameters

### -param contextAlternator

This parameter points to a IDebugHostContextAlternator pointer, which is used to retrieve the context alternator. This parameter is an Output parameter.

## -returns

Returns an HRESULT indicating the success or failure of the method. 

## -remarks

## -see-also

[IDebugHostContextControl interface](nn-dbgmodel-idebughostcontextcontrol.md)