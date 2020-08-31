---
UID: NF:dbgmodel.IEquatableConcept.AreObjectsEqual
title: IEquatableConcept::AreObjectsEqual (dbgmodel.h)
description: Compares this object to another (of arbitrary type) for equality.  If the comparison cannot be performed, E_NOT_SET should be returned.
ms.assetid: 846d56f6-e5e2-411d-ae4b-5dc1e31e3221
ms.date: 09/26/2018
keywords: ["IEquatableConcept::AreObjectsEqual"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IEquatableConcept::AreObjectsEqual
 - dbgmodel/IEquatableConcept::AreObjectsEqual
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IEquatableConcept.AreObjectsEqual
---

# IEquatableConcept::AreObjectsEqual


## -description

Compares this object to another (of arbitrary type) for equality.  If the comparison cannot be performed, E_NOT_SET should be returned.
[IEquatableConcept](nn-dbgmodel-iequatableconcept.md) is typically implemented by the object creators.  To compare objects consider using [IModelObject](nn-dbgmodel-imodelobject.md)::IsEqualTo or [IModelObject](nn-dbgmodel-imodelobject.md)::Compare.

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

Generally speaking, you will implement (but not necessarily consume) [IEquatableConcept](nn-dbgmodel-iequatableconcept.md).  It can be easier to call [IModelObject](nn-dbgmodel-imodelobject.md)::IsEqualTo or [IModelObject](nn-dbgmodel-imodelobject.md)::Compare and let those methods manage the concept fetch.

## -see-also

[IEquatableConcept interface](nn-dbgmodel-iequatableconcept.md)

