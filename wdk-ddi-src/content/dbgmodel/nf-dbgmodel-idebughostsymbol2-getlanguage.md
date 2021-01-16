---
UID: NF:dbgmodel.IDebugHostSymbol2.GetLanguage
title: IDebugHostSymbol2::GetLanguage (dbgmodel.h)
description: If the symbol can identify the language for which it applies, this returns an identifier for such.
ms.date: 09/28/2018
keywords: ["IDebugHostSymbol2::GetLanguage"]
ms.keywords: IDebugHostSymbol2::GetLanguage, GetLanguage, IDebugHostSymbol2.GetLanguage, IDebugHostSymbol2::GetLanguage, IDebugHostSymbol2.GetLanguage
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostSymbol2::GetLanguage
 - dbgmodel/IDebugHostSymbol2::GetLanguage
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbol2::GetLanguage
---

# IDebugHostSymbol2::GetLanguage


## -description

If the symbol can identify the language for which it applies, this returns an identifier for such. Many symbols will *NOT* be able to make this determination.  In such cases, this method will fail.

It is also possible that the host does not understand the language or there is no defined LanguageKind. In such cases, LanguageUnknown will be returned and the method will succeed.

## -parameters

### -param pKind

If it is possible to determine from the symbolic information, the language in which the given symbol was defined is returned here.  This may be indeterminate for many symbols.

## -returns

This method returns HRESULT which indicate success or failure.

## -remarks

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)

