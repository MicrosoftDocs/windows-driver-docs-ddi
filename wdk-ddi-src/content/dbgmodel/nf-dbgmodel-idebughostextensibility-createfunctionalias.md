---
UID: NF:dbgmodel.IDebugHostExtensibility.CreateFunctionAlias
title: IDebugHostExtensibility::CreateFunctionAlias
author: windows-driver-content
description: The CreateFunctionAlias method creates a "function alias", a "quick alias" for a method implemented in some extension. The meaning of this alias is host specific.
ms.assetid: 73d90254-12bd-478b-a80e-57d15ea88ca8
ms.date: 09/12/2018 
ms.topic: method
ms.keywords: IDebugHostExtensibility::CreateFunctionAlias, CreateFunctionAlias, IDebugHostExtensibility.CreateFunctionAlias, IDebugHostExtensibility::CreateFunctionAlias, IDebugHostExtensibility.CreateFunctionAlias
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
-	IDebugHostExtensibility.CreateFunctionAlias
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostExtensibility::CreateFunctionAlias


## -description

The CreateFunctionAlias method creates a "function alias", a "quick alias" for a method implemented in some extension. The meaning of this alias is host specific. It may extend the host's expression evaluator with the function or it may do something entirely different. 

For Debugging Tools for Windows, a function alias: 

- Is accessible in the expression evaluator through the @$ symbol. A function alias registered under someName is callable in the evaluator via @$someName(...).

- Can be invoked via the older bang syntax. The invocation "!someName arg1, arg2, ..." is semantically equivalent to running the (dx) expression evaluator with "@$someName(arg1, arg2, ...)" and displaying the result.


## -parameters

### -param aliasName
The (quick) name of the alias being created/registered.

### -param functionObject
A data model method (an IModelMethod boxed into an IModelObject) which implements the functionality of the function alias.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks
**Sample Code**

```cpp
class MySumFunction:
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IModelMethod
        >
{
public:

    IFACEMETHOD(Call)(_In_ IModelObject * /*pContextObject*/, 
                      _In_ ULONG64 argCount, 
                      _In_reads_(argCount) IModelObject **ppArguments, 
                      _COM_Errorptr_ **ppResult)
    {
        HRESULT hr = S_OK;
        *ppResult = nullptr;

        if (argCount == 0)
        {
            return E_INVALIDARG;
        }

        int sum = 0;
        for (ULONG64 i = 0; i < argCount; ++i)
        {
            VARIANT vtValue;
            if (FAILED(ppArguments[i]->GetIntrinsicValueAs(&vtValue)))
            {
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

// Create a method object and register it as a function alias.
ComPtr<MySumFunction> spSumFunc = Microsoft::WRL::Make<MySumFunction>();
if (spSumFunc != nullptr)
{
    VARIANT vtMethod;
    vtMethod.vt = VT_UNKNOWN;
    vtMethod.punkVal = static_cast<IModelMethod *>(spSumFunc.Get());
    
    ComPtr<IModelObject> spMethodObject;
    if (SUCCEEDED(GetManager()->CreateIntrinsicObject(ObjectMethod, 
                                                      &vtMethod, 
                                                      &spMethodObject)))
    {
        ComPtr<IDebugHostExtensibility> spHostExtensibility;
        if (SUCCEEDED(GetHost()->QueryInterface(IID_PPV_ARGS(&spHostExtensibility)))
        {
            if (SUCCEEDED(spHostExtensibility->RegisterFunctionAlias(
                L"sumit", 
                spMethodObject.Get())))
            {
                // sumit is now an alias for our function.  The meaning here 
                // is host specific.  For DbgEng, it means you can do things
                // like "dx @$sumit(5, 7, 8)" or "!sumit 5, 7, 8"
            }
        }
    }
}
```


## -see-also

[IDebugHostExtensibility interface](nn-dbgmodel-idebughostextensibility.md)
