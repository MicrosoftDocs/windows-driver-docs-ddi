---
UID: NF:dbgmodel.IDebugHostEvaluator.EvaluateExpression
title: IDebugHostEvaluator::EvaluateExpression (dbgmodel.h)
description: The EvaluateExpression method allows requests the debug host to evaluate a language (that is C++) expression and return the resulting value of that expression evaluation boxed as an IModelObject.
ms.assetid: 3a5d84d6-39ba-46c0-a4e7-4e8134aa1b1a
ms.date: 09/12/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostEvaluator.EvaluateExpression"
ms.keywords: IDebugHostEvaluator::EvaluateExpression, EvaluateExpression, IDebugHostEvaluator.EvaluateExpression, IDebugHostEvaluator::EvaluateExpression, IDebugHostEvaluator.EvaluateExpression
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
- IDebugHostEvaluator.EvaluateExpression
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostEvaluator::EvaluateExpression


## -description

The EvaluateExpression method allows requests the debug host to evaluate a language (e.g.: C++) expression and return the resulting value of that expression evaluation boxed as an [IModelObject](nn-dbgmodel-imodelobject.md). This particular variant of the method only allows language constructs. Any additional functionality which is presented within the expression evaluator of the debug host that is not present in the language (e.g.: LINQ query methods) is turned off for the evaluation. 

Because this method only uses things which are defined by the language being debugged, this method is portable and safe to use from host to host. A debug host which implements debugging for a particular language should evaluate an expression via this method in the same way as any other host which debugs the same language. As such, this is the preferred method for doing expression evaluation. 


## -parameters

### -param context
The host context in which the expression evaluation occurs. If there are, for instance, memory reads of the target due to pointer dereferences, the address space in which those memory reads are made is given by this argument.

### -param expression
The language expression to be evaluated. This string may only contain an expression which is valid in the language being debugged. It may not contain any additional constructs which may be available in the debug host's expression evaluator.

### -param bindingContext
The binding context in which symbol (variable) names will be looked up. For C++, this is semantically equivalent to the this pointer value.

### -param result
The resulting value of the expression evaluation will be returned here.

### -param metadata
Any metadata associated with the expression or result is returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHost> spHost;   /* get the host */
ComPtr<IModelObject> spThis; /* get some object, an example here: some native 
                                object with fields m_intVal and m_intVal2 */

ComPtr<IDebugHostEvaluator> spEval;
if (SUCCEEDED(spHost.As(&spEval)))
{
    ComPtr<IModelObject> spResult;
    ComPtr<IKeyStore> spMetadata;
    if (SUCCEEDED(spEval->EvaluateExpression(
        USE_CURRENT_HOST_CONTEXT, 
        L"m_intVal + this->m_intVal2", 
        spThis.Get(), 
        &spResult, 
        &spMetadata)))
    {
        // spResult will have the result of a language evaluation of 
        // "m_intVal + this->m_intVal2" where the name binding context 
        // (e.g.: *this* pointer) is spThis
        // spMetadata will have any additional metadata (e.g.: display radix, etc...)
    }
}
```


## -see-also

[IDebugHostEvaluator interface](nn-dbgmodel-idebughostevaluator.md)
