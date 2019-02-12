---
UID: NF:dbgmodel.IModelKeyReference2.OverrideContextObject
title: IModelKeyReference2::OverrideContextObject (dbgmodel.h)
description: The OverrideContextObject method is an method which is used to permanently alter the context object which this key reference will pass to any underlying property accessor's GetValue or SetValue methods.
ms.assetid: bb28b47c-7311-4572-9d87-0331a5cc728a
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference2::OverrideContextObject, OverrideContextObject, IModelKeyReference2.OverrideContextObject, IModelKeyReference2::OverrideContextObject, IModelKeyReference2.OverrideContextObject
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
-	IModelKeyReference2.OverrideContextObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelKeyReference2::OverrideContextObject


## -description

The OverrideContextObject method (only present on IModelKeyReference2) is an advanced method which is used to permanently alter the context object which this key reference will pass to any underlying property accessor's GetValue or SetValue methods. The object passed to this method will also be returned from a call to GetContextObject. This method can be used by script providers to replicate certain dynamic language behaviors. Most clients should not call this method. 

## -parameters

### -param newContextObject
The new context object to pass to any underlying property accessor's GetValue or SetValue methods.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject;          /* get an object */
ComPtr<IModelObject> spAdjustedContext; /* get the object you'd like to adjust context to */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    // At this moment, spKeyRef->GetContextObject() and 
    // spKeyRef->GetOriginalObject() will return the same value
    ComPtr<IModelKeyReference2> spKeyRef2;
    if (SUCCEEDED(spKeyRef.As(&spKeyRef2)))
    {
        if (SUCCEEDED(spKeyRef2->OverrideContextObject(spAdjustedContext.Get())))
        {
            // Now, spKeyRef->GetContextObject() will return spAdjustedContext 
            // and spKeyRef->GetOriginalObject() will return spObject
            // Very few clients will want to do this.  It is useful for some 
            // bridges between dynamic languages and the data model.
        }
    }
}
```

## -see-also

[IModelKeyReference2 interface](nn-dbgmodel-imodelkeyreference2.md)
