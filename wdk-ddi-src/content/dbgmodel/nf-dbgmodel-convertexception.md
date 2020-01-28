---
UID: NF:dbgmodel.ConvertException
title: ConvertException function (dbgmodel.h)
description: Trap and convert all exceptions coming out of a functor to an appropriate HRESULT.
ms.assetid: cd951fc0-c5a0-4e62-ad33-cfc6a834d849
ms.date: 09/28/2018
f1_keywords:
 - "dbgmodel/ConvertException"
ms.keywords: ConvertException
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
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- ConvertException
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# ConvertException function


## -description

Trap and convert all exceptions coming out of a functor to an appropriate HRESULT.

C++ Specific API Helper.

## -parameters

### -param fn
An HRESULT returning functor.  If the functor throws an exception, the exception will be caught and converted to an HRESULT.


## -returns
This function returns HRESULT.
## -remarks

## -see-also
