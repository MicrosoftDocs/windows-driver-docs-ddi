---
UID: NF:dbgmodel.IComparableConcept.CompareObjects
title: IComparableConcept::CompareObjects
author: windows-driver-content
description: TBD
ms.assetid: c9736b52-f159-4468-af0a-94b409c89991
ms.author: windowsdriverdev
ms.date: 09/11/2018
ms.topic: method
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IComparableConcept.CompareObjects
product: Windows
targetos: Windows


---

# IComparableConcept::CompareObjects


## -description

 Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.
    
 The return value passed in comparison result has the following meaning:
    
       < 0 : contextObject < otherObject
         0 : contextObject == otherObject
       > 0 : contextObject > otherObject

## -parameters

### -param contextObject
TBD

### -param otherObject
TBD

### -param comparisonResult
TBD

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IComparableConcept interface](nn-dbgmodel-icomparableconcept.md)