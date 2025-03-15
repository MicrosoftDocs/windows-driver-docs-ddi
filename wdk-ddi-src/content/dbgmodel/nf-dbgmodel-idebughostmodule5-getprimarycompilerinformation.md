---
UID: NF:dbgmodel.IDebugHostModule5.GetPrimaryCompilerInformation
tech.root: debugger
title: IDebugHostModule5::GetPrimaryCompilerInformation
ms.date: 02/24/2025
targetos: Windows
description: The GetPrimaryCompilerInformation method Returns information about what might be considered the "primary compiler" which produced the module.
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
 - IDebugHostModule5::GetPrimaryCompilerInformation
f1_keywords:
 - IDebugHostModule5::GetPrimaryCompilerInformation
 - dbgmodel/IDebugHostModule5::GetPrimaryCompilerInformation
dev_langs:
 - c++
helpviewer_keywords:
 - GetPrimaryCompilerInformation
---

## -description

The GetPrimaryCompilerInformationmethod retrieves information regarding the "primary compiler" which produced the module. The returned information can be used, for example, to understand how symbols are formatted by that compiler. Although this can vary for each compilation unit or compiland, this method should return the details of the "primary" or most significant one for non-assembly compilation units.

It is important to note that the "compiler string" returned may either be a compiler name or it may contain additional information such as command line arguments depending on the underlying implementation. It is also possible for a debug host to return E_NOTIMPL for this call.

## -parameters

### -param pCompilerId

Pointer to where the identifier of the primary compiler will be stored.

### -param pPrimaryCompilerString

Optional pointer to where the string representation of the primary compiler will be stored.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule5 interface](nn-dbgmodel-idebughostmodule5.md)