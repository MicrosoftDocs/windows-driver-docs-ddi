---
UID: NF:dbgmodel.IDebugHostSymbol2.GetLanguage
title: IDebugHostSymbol2::GetLanguage
author: windows-driver-content
description: TBD
ms.assetid: b97fb7f8-ccd2-4450-b1fb-a3ea218889ec
ms.author: windowsdriverdev
ms.date: 09/20/2018
ms.topic: method
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
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostSymbol2.GetLanguage
product: Windows
targetos: Windows


---

# IDebugHostSymbol2::GetLanguage

## -description

If the symbol can identify the language for which it applies, this returns an identifier for such. Many symbols will *NOT* be able to make this determination.  In such cases, this method will fail.

It is also possible that the host does not understand the language or there is no defined LanguageKind. In such cases, LanguageUnknown will be returned and the method will succeed.

## -parameters

### -param pKind


## -returns
This method returns HRESULT which indicate success or failure.

## -remarks

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)