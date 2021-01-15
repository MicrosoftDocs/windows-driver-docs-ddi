---
UID: NF:dbgmodel.IDebugHostTypeSignature.IsMatch
title: IDebugHostTypeSignature::IsMatch (dbgmodel.h)
description: The IsMatch method returns an indication of whether a particular type instance matches the criteria specified in the type signature.
ms.date: 09/10/2018
keywords: ["IDebugHostTypeSignature::IsMatch"]
ms.keywords: IDebugHostTypeSignature::IsMatch, IsMatch, IDebugHostTypeSignature.IsMatch, IDebugHostTypeSignature::IsMatch, IDebugHostTypeSignature.IsMatch
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
 - IDebugHostTypeSignature::IsMatch
 - dbgmodel/IDebugHostTypeSignature::IsMatch
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostTypeSignature::IsMatch
---

# IDebugHostTypeSignature::IsMatch


## -description

The IsMatch method returns an indication of whether a particular type instance matches the criteria specified in the type signature. If it does, an indication of this is returned as well as an enumerator which will indicate all of the specific portions of the type instance (as symbols) which matched wildcards in the type signature.

## -parameters

### -param type

The type instance to compare against the type signature.

### -param isMatch

An indication of whether the type instance matches the type signature is returned here.

### -param wildcardMatches

If the type instance matches the type signature, an enumerator will be returned here which will enumerate all the specific portions of the type instance (as symbols) which matched wildcards in the type signature.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostSymbols> spSym; /* get the host's symbols interface */
ComPtr<IDebugHostType> spType;   /* get a type */

ComPtr<IDebugHostTypeSignature> spSig;
if (SUCCEEDED(spSym->CreateTypeSignature(L"MyTemplateType<*>", 
                                         nullptr, 
                                         &spSig)))
{
    bool isMatch;
    ComPtr<IDebugHostSymbolEnumerator> spWildcardEnum;
    if (SUCCEEDED(spSig->IsMatch(spType.get(), &isMatch, &spWildcardEnum)))
    {
        // isMatch will contain whether the type matches the signature (whether 
        // it is a MyTemplateType template with *ANY* template arguments
        if (isMatch)
        {
            // spWildcardEnum will contain what the '*' in 'MyTemplateType<*>' 
            // matched against.  This may be one or more template arguments in 
            // linear order.  An IDebugHostType would be present for type arguments.
        }
    }
}
```

## -see-also

[IDebugHostTypeSignature interface](nn-dbgmodel-idebughosttypesignature.md)

