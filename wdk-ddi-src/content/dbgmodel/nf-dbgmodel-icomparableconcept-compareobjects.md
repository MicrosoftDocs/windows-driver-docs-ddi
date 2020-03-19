---
UID: NF:dbgmodel.IComparableConcept.CompareObjects
title: IComparableConcept::CompareObjects (dbgmodel.h)
description: Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.
ms.assetid: c9736b52-f159-4468-af0a-94b409c89991
ms.date: 09/28/2018
keywords: ["IComparableConcept::CompareObjects"]
f1_keywords:
 - "dbgmodel/IComparableConcept.CompareObjects"
ms.keywords: IComparableConcept::CompareObjects, CompareObjects, IComparableConcept.CompareObjects, IComparableConcept::CompareObjects, IComparableConcept.CompareObjects
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
- IComparableConcept.CompareObjects
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IComparableConcept::CompareObjects


## -description

 Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.
    
 The return value passed in comparison result has the following meaning:

```text 
< 0 : contextObject < otherObject

0 : contextObject == otherObject

> 0 : contextObject > otherObject
```

## -parameters

### -param contextObject
The object which is being compared.  This should be the same object from which the comparable concept was acquired.

### -param otherObject
The object to compare to.

### -param comparisonResult
The result of the comparison will be returned here.  If the returned value is less than 0, contextObject is less than otherObject.  If the returned value is zero, they are equal.  If the returned value is greater than zero, contextObject is greater than otherObject.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IComparableConcept interface](nn-dbgmodel-icomparableconcept.md)
