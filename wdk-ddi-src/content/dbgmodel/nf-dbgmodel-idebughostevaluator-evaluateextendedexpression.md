---
UID: NF:dbgmodel.IDebugHostEvaluator.EvaluateExtendedExpression
title: IDebugHostEvaluator::EvaluateExtendedExpression
description: The EvaluateExtendedExpression method is similar to the EvaluateExpression method except that it turns back on additional non-language functionality which a particular debug host chooses to add to its expression evaluator. 
ms.assetid: 0bbe45cb-f806-4b3e-a042-d13a15a96e8c
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDebugHostEvaluator::EvaluateExtendedExpression, EvaluateExtendedExpression, IDebugHostEvaluator.EvaluateExtendedExpression, IDebugHostEvaluator::EvaluateExtendedExpression, IDebugHostEvaluator.EvaluateExtendedExpression
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
-	IDebugHostEvaluator.EvaluateExtendedExpression
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostEvaluator::EvaluateExtendedExpression


## -description

The EvaluateExtendedExpression method is similar to the EvaluateExpression method except that it turns back on additional non-language functionality which a particular debug host chooses to add to its expression evaluator. For Debugging Tools for Windows, for example, this enables anonymous types, LINQ queries, module qualifiers, format specifiers, and other non-C/C++ functionality. 

It is important to note that there is no guarantee that an expression which evaluates against one host via EvaluateExtendedExpression will evaluate correctly against another host which debugs the same language. Extensions in the expression evaluator are the purview of a given host. It is strongly recommended that clients utilize the EvaluateExpression method instead of the EvaluateExtendedExpression method for this exact reason. Using this method reduces the portability of the caller. 


## -parameters

### -param context
The host context in which the expression evaluation occurs. If there are, for instance, memory reads of the target due to pointer dereferences, the address space in which those memory reads are made is given by this argument.

### -param expression
The expression to be evaluated. This may use host private extensions to the language syntax.

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
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostEvaluator> spEval;
if (SUCCEEDED(spHost.As(&spEval)))
{
    ComPtr<IModelObject> spNotepadProcesses;

    // We can use any syntax that's private to the host (not only 
    // language syntax).  This is not necessarily portable from host to host
    if (SUCCEEDED(spEval->EvaluateExtendedExpression(
        USE_CURRENT_HOST_CONTEXT, 
        L"@$cursession->Processes.Where(p => p.Name == \"notepad.exe\")", 
        nullptr, 
        &spNotepadProcesses, 
        nullptr)))
    {
        // spNotepadProcesses will contain a collection of every process 
        // named (exactly) "notepad.exe".  Such can be iterated with IIterableConcept.
    }
}
```


## -see-also

[IDebugHostEvaluator interface](nn-dbgmodel-idebughostevaluator.md)
