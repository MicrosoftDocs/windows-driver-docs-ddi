---
UID: NF:dbgmodel.IPreferredRuntimeTypeConcept.CastToPreferredRuntimeType
title: IPreferredRuntimeTypeConcept::CastToPreferredRuntimeType
author: windows-driver-content
description: TBD
ms.assetid: cdb65537-36e9-4c2c-aa0f-1a9c2cf74164
ms.author: windowsdriverdev
ms.date: 09/20/2018 
ms.topic: method
ms.keywords: IPreferredRuntimeTypeConcept::CastToPreferredRuntimeType, CastToPreferredRuntimeType, IPreferredRuntimeTypeConcept.CastToPreferredRuntimeType, IPreferredRuntimeTypeConcept::CastToPreferredRuntimeType, IPreferredRuntimeTypeConcept.CastToPreferredRuntimeType
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
-	IPreferredRuntimeTypeConcept.CastToPreferredRuntimeType
product: Windows
targetos: Windows


tech.root: debugger
---

# IPreferredRuntimeTypeConcept::CastToPreferredRuntimeType


## -description

The CastToPreferredRuntimeType method is called whenever a client wishes to attempt to convert from a static type instance to the runtime type of that instance. If the object in question supports (through one of its attached parent models) the preferred runtime type concept, this method will be called to perform the conversion. This method may either return the original object (there is no conversion or it could not be analyzed), return a new instance of the runtime type, fail for non-semantic reasons (e.g.: out of memory), or return E_NOT_SET. The E_NOT_SET error code is a very special error code which indicates to the data model that the implementation does not want to override the default behavior and that the data model should fall back to whatever analysis is performed by the debug host (e.g.: RTTI analysis, examination of the shape of the virtual function tables, etc...) 

## -parameters

### -param contextObject
The statically typed instance object (this pointer) for which to perform analysis and attempt to downcast to the runtime type.

### -param object
If a conversion to a runtime type occurred, this is a new instance typed according to the runtime type. If the analysis could not be performed or there was no change in type, this may be the original object.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Example Implementation:**

```cpp
IFACEMETHOD(CastToPreferredRuntimeType)(_In_ IModelObject *pContextObject, 
                                        _COM_Outptr_ IModelObject **ppRuntimeObject)
{
    HRESULT hr = S_OK;
    *ppRuntimeObject = nullptr;

    ComPtr<IModelObject> spRuntimeObject;

    // Imagine this was on a class for a data model registered against some 
    // IFoo type where IFoo was always backed by CFoo (the type of which is 
    // stored in m_spType) and the offset between IFoo and CFoo was m_runtimeOffset.
    Location loc;
    hr = pContextObject->GetLocation(&loc);
    if (SUCCEEDED(hr))
    {
        loc.Offset -= m_runtimeOffset;

        // By passing 'nullptr' as the context, it will inherit its context 
        // from the passed type.  Sufficient for *THIS* purpose in *MOST* cases.
        hr = GetManager()->CreateTypedObject(nullptr, 
                                             loc, 
                                             m_spType.Get(), 
                                             &spRuntimeObject);
    }

    if (SUCCEEDED(hr))
    {
        *ppRuntimeObject = spRuntimeObject.Detach();
    }

    return hr;
}
```


## -see-also

[IPreferredRuntimeTypeConcept interface](nn-dbgmodel-ipreferredruntimetypeconcept.md)

