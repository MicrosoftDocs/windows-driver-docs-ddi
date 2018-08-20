---
UID: NF:dbgmodel.IModelObject.GetIntrinsicValueAs
title: IModelObject::GetIntrinsicValueAs
author: windows-driver-content
description: TBD
ms.assetid: 5fa25457-b1fc-4f9c-b576-48c087aacff7
ms.author: windowsdriverdev
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetIntrinsicValueAs, GetIntrinsicValueAs, IModelObject.GetIntrinsicValueAs, IModelObject::GetIntrinsicValueAs, IModelObject.GetIntrinsicValueAs
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
-	IModelObject.GetIntrinsicValueAs
product: Windows
targetos: Windows


---

# IModelObject::GetIntrinsicValueAs


## -description

The GetIntrinsicValueAs method behaves much as the GetIntrinsicValue method excepting that it converts the value to the specified variant type. If the conversion cannot be performed, the method returns an error. 

## -parameters

### -param vt
The type of value to convert to is passed here as a VARTYPE. Legal values are VT_I1 through VT_I8, VT_U1 through VT_U8, VT_R4 through VT_R8, and VT_BOOL. String conversions cannot be performed through this method.

### -param intrinsicData
The value boxed inside the IModelObject converted to the type described by the vt argument is returned here. The pointer must point to a VARIANT structure which does not contain a freeable value. It is the responsibility of the caller to clear this VARIANT with VariantClear when finished with it.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```
ComPtr<IModelObject> spObject; /* get from somewhere */

// Unbox as VT_I4.  This will fail if the value does not FIT into an int (I4):
VARIANT vtVal;
HRESULT hr = spObject->GetIntrinsicValueAs(VT_I4, &vtVal);
if (SUCCEEDED(hr))
{
    int iVal = vtVal.lVal; // The object has successfully packed into an I4 and been unboxed as an int.
}
// Since we know this is a VT_I4, VariantClear is superfluous.
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)