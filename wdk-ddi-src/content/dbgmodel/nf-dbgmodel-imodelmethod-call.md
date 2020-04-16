---
UID: NF:dbgmodel.IModelMethod.Call
title: IModelMethod::Call (dbgmodel.h)
description: The Call method is the way in which any method defined in the data model is invoked. 
ms.assetid: 217feb09-ddbf-407c-a8a4-1144d7dd7c41
ms.date: 08/13/2018
keywords: ["IModelMethod::Call"]
f1_keywords:
 - "dbgmodel/IModelMethod.Call"
ms.keywords: IModelMethod::Call, Call, IModelMethod.Call, IModelMethod::Call, IModelMethod.Call
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
- IModelMethod.Call
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelMethod::Call


## -description

The Call method is the way in which any method defined in the data model is invoked. The caller is responsible for passing an accurate instance object (this pointer) and an arbitrary set of arguments. The result of the method and any optional metadata associated with that result is returned. Methods which do not logically return a value still must return a valid [IModelObject](nn-dbgmodel-imodelobject.md). In such a case, the [IModelObject](nn-dbgmodel-imodelobject.md) is a boxed no value. In the event a method fails, it may return optional extended error information in the input argument (even if the returned HRESULT is a failure). It is imperative that callers check for this. 

An underlying method may choose to provide its own implementation of "overload resolution" performing different actions based on the actual types or quantity of its input arguments. The data model provides no assistance for such. 

## -parameters

### -param pContextObject
The context object (instance this pointer) from which the method was fetched.

### -param argCount
The number of arguments being passed to the method call.

### -param ppArguments
An array of [IModelObject](nn-dbgmodel-imodelobject.md) objects, one for each argument in the call.

### -param ppResult
The return value of the call. In the event that the call semantically returns nothing, a boxed no value object will be returned. Should the call fail (as indicated by a failing HRESULT), optional extended error information may be present here.

### -param ppMetadata
Optional metadata about the call result may be placed here.


## -returns
This method returns HRESULT that indicates success or failure. 

## -remarks

**Sample Code**

```cpp
// The full implementation class is shown for clarity.  This is a method which sums up all integers passed to it.
class MySummationMethod :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IModelMethod
        >
{
public:

    // The method is 'static'.  Ignore pContextObject.
    IFACEMETHOD(Call)(_In_ IModelObject * /*pContextObject*/, 
                      _In_ ULONG64 argCount, 
                      _In_reads_(argCount) IModelObject **ppArguments, 
                      _COM_Errorptr_ IModelObject **ppResult,
                      _COM_Outptr_opt_result_maybenull_ IKeyStore **ppMetadata)
    {
        HRESULT hr = S_OK;
        *ppResult = nullptr;
        if (ppMetadata != nullptr)
        {
             *ppMetadata = nullptr;
        }

        if (argCount == 0)
        {
            // Example of a specific error message.
            GetManager()->CreateErrorObject(
                E_INVALIDARG, 
                L"At least one argument must be passed to the Sum() method", 
                ppResult);
            return E_INVALIDARG;
        }

        int sum = 0;
        for (ULONG64 i = 0; i < argCount; ++i)
        {
            VARIANT vtValue;
            hr = ppArguments[i]->GetIntrinsicValueAs(VT_I4, &vtValue);
            if (FAILED(hr))
            {
                // If we couldn't unbox as I4, someone passed an invalid argument.
                // As an example, be specific.
                GetManager()->CreateErrorObject(
                    E_INVALIDARG, 
                    L"All arguments passed to the Sum() method must be integers", 
                    ppResult);
                return E_INVALIDARG;
            }

            sum += vtValue.lVal;
        }

        VARIANT vtSum;
        vtSum.vt = VT_I4;
        vtSum.lVal = sum;

        ComPtr<IModelObject> spSum;
        hr = GetManager()->CreateIntrinsicObject(ObjectIntrinsic, &vtSum, &spSum);
        if (SUCCEEDED(hr))
        {
            *ppResult = spSum.Detach();
        }
        return hr;
    }
};
```

## -see-also

[IModelMethod interface](nn-dbgmodel-imodelmethod.md)
