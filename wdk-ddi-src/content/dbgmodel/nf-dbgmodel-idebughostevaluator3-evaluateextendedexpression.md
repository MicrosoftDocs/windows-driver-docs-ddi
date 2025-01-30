---
UID: NF:dbgmodel.IDebugHostEvaluator3.EvaluateExtendedExpression
tech.root: debugger
title: IDebugHostEvaluator3::EvaluateExtendedExpression
ms.date: 01/20/2025
targetos: Windows
description: The EvaluateExtendedExpression method requests an evaluation of a language expression including any additional non-language evaluation.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostEvaluator3::EvaluateExtendedExpression
f1_keywords:
 - IDebugHostEvaluator3::EvaluateExtendedExpression
 - dbgmodel/IDebugHostEvaluator3::EvaluateExtendedExpression
dev_langs:
 - c++
helpviewer_keywords:
 - EvaluateExtendedExpression
---

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

ComPtr<IDebugHostEvaluator2> spEval;
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

[IDebugHostEvaluator3 interface](nn-dbgmodel-idebughostevaluator3.md)