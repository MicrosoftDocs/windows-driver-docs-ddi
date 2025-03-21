---
UID: NF:dbgmodel.IDebugHostModule3.GetRange
tech.root: debugger
title: IDebugHostModule3::GetRange
ms.date: 02/24/2025
targetos: Windows
description: The GetRange method retrieves the beginning and ending virtual addresses (VA) of the module in memory.
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
 - IDebugHostModule3::GetRange
f1_keywords:
 - IDebugHostModule3::GetRange
 - dbgmodel/IDebugHostModule3::GetRange
dev_langs:
 - c++
helpviewer_keywords:
 - GetRange
---

## -description

The GetRange method retrieves the beginning and ending virtual addresses (VA) of the module in memory.

## -parameters

### -param moduleStart

Pointer to where the starting virtual address of the module will be stored.

### -param moduleEnd

Pointer to where the ending virtual address of the module will be stored.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)