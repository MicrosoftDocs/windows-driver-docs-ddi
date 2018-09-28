---
UID: NF:dbgmodel.IEquatableConcept.AreObjectsEqual
title: IEquatableConcept::AreObjectsEqual
author: windows-driver-content
description: TBD
ms.assetid: 846d56f6-e5e2-411d-ae4b-5dc1e31e3221
ms.author: windowsdriverdev
ms.date: 09/26/2018
ms.topic: method
ms.keywords: IEquatableConcept::AreObjectsEqual, AreObjectsEqual, IEquatableConcept.AreObjectsEqual, IEquatableConcept::AreObjectsEqual, IEquatableConcept.AreObjectsEqual
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
-	IEquatableConcept.AreObjectsEqual
product: Windows
targetos: Windows


tech.root: debugger
---

# IEquatableConcept::AreObjectsEqual


## -description

Compares this object to another (of arbitrary type) for equality.  If the comparison cannot be performed, E_NOT_SET should be returned.
IEquatableConcept is typically implemented by the object creators.  To compare objects consider using IModelObject::IsEqualTo or IModelObject::Compare.

## -parameters

### -param contextObject
The object being compared.

### -param otherObject
The other object (of arbitrary type) that contextObject is being compared to.


### -param isEqual
Returned Boolean indicating if the two objects are equal. 


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

Generally speaking, you will implement (but not necessarily consume) IEquatableConcept.  It can be easier to call IModelObject::IsEqualTo or IModelObject::Compare and let those methods manage the concept fetch.


## -see-also

[IEquatableConcept interface](nn-dbgmodel-iequatableconcept.md)
