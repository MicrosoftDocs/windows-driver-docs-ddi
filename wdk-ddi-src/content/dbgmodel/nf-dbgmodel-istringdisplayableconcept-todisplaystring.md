---
UID: NF:dbgmodel.IStringDisplayableConcept.ToDisplayString
title: IStringDisplayableConcept::ToDisplayString (dbgmodel.h)
description: The ToDisplayString method is called whenever a client wishes to convert an object into a string to display (to console, in the UI, etc...).
ms.assetid: e6823fca-e9c4-4e2a-8c0f-95bd9f7527e9
ms.date: 10/05/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IStringDisplayableConcept.ToDisplayString"
ms.keywords: IStringDisplayableConcept::ToDisplayString, ToDisplayString, IStringDisplayableConcept.ToDisplayString, IStringDisplayableConcept::ToDisplayString, IStringDisplayableConcept.ToDisplayString
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
- IStringDisplayableConcept.ToDisplayString
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IStringDisplayableConcept::ToDisplayString


## -description

The ToDisplayString method is called whenever a client wishes to convert an object into a string to display (to console, in the UI, etc...). Such a string conversion should not be used for the basis of additional programmatic manipulation. The string conversion itself may be deeply influenced by the metadata passed to the call. A string conversion should make every attempt to honor the PreferredRadix and PreferredFormat keys. 

## -parameters

### -param contextObject
The instance (this pointer) being converted to a display string is passed in this argument.

### -param metadata
An optional metadata store which defines how the caller would like the string to be converted. The implementation should make every attempt to honor the requests in the store (in particular, the PreferredRadix and PreferredFormat keys).

### -param displayString
The string conversion as allocated by the SysAllocString function will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IStringDisplayableConcept interface](nn-dbgmodel-istringdisplayableconcept.md)
