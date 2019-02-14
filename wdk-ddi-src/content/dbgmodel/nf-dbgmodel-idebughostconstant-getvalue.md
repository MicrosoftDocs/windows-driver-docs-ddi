---
UID: NF:dbgmodel.IDebugHostConstant.GetValue
title: IDebugHostConstant::GetValue (dbgmodel.h)
description: The GetValue method returns the value of the constant packed into a VARIANT. 
ms.assetid: 8cf871cc-c21e-44ee-bd5a-bf3b4b1ad7b4
ms.date: 10/03/2018
ms.topic: method
ms.keywords: IDebugHostConstant::GetValue, GetValue, IDebugHostConstant.GetValue, IDebugHostConstant::GetValue, IDebugHostConstant.GetValue
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
-	IDebugHostConstant.GetValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostConstant::GetValue

## -description
The GetValue method returns the value of the constant packed into a VARIANT. 

It is important to note that the GetType method on IDebugHostSymbol may return a specific type symbol for the constant. In such cases, there is no guarantee that the packing of the constant value as defined by the type symbol is the same as the packing as returned by the GetValue method here. 

## -parameters

### -param value
The value of the data packed into a VARIANT will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostConstant> spConstant; /* get a constant */

VARIANT vtValue;
if (SUCCEEDED(spConstant->GetValue(&vtValue)))
{
    // vtValue contains the value of the constant.  The variant type of vtValue 
    // may not match what the type indicates if you get the type of the symbol.
    VariantClear(&vtValue);
}
```

## -see-also
[IDebugHostConstant interface](nn-dbgmodel-idebughostconstant.md)
