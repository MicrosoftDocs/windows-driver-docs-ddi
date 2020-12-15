---
UID: NF:dbgmodel.IDebugHostEvaluator2.AssignTo
title: IDebugHostEvaluator2::AssignTo (dbgmodel.h)
description: The AssignTo method performs assignment according to the semantics of the language being debugged.
ms.date: 09/12/2018
keywords: ["IDebugHostEvaluator2::AssignTo"]
ms.keywords: IDebugHostEvaluator2::AssignTo, AssignTo, IDebugHostEvaluator2.AssignTo, IDebugHostEvaluator2::AssignTo, IDebugHostEvaluator2.AssignTo
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
 - IDebugHostEvaluator2::AssignTo
 - dbgmodel/IDebugHostEvaluator2::AssignTo
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostEvaluator2.AssignTo
---

# IDebugHostEvaluator2::AssignTo


## -description

The AssignTo method performs assignment according to the semantics of the language being debugged.

## -parameters

### -param assignmentReference

A reference to the thing being assigned. While this can be either a model based reference (e.g.: an ObjectTargetObjectReference) or a language reference (e.g.: a C++ &), it must be some type of reference (an LVALUE).

### -param assignmentValue

The value being assigned to what is referenced via the assignmentReference argument. Note that this value may be coerced or converted according to language rules before being assigned.

### -param assignmentResult

The result of assignment, if successful. If not, optionally, an extended error object indicating why the assignment failed. Note that result of assignment in this case is what the language defines as the result of an assignment operation. For C++, this would be a language reference to the thing assigned.

### -param assignmentMetadata

Any optional metadata associated with the assignment result is returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHost> spHost;           /* get the host */
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IModelObject> spObject;       /* get an object; for an example - consider a
                                        'class MyClass' with an integer value 
                                        m_intVal */

ComPtr<IDebugHostEvaluator2> spEval2;
if (SUCCEEDED(spHost.As(&spEval2)))
{
    // Get a reference to the m_intVal field
    ComPtr<IModelObject> spIntValRef;
    if (SUCCEEDED(spObject->GetRawReference(SymbolField, 
                                            L"m_intVal", 
                                            RawSearchNone, 
                                            &spIntValRef)))
    {
        // Box some value we want to assign.
        VARIANT vtVal;
        vtVal.vt = VT_UI8;
        vtVal.ullVal = 123456;

        ComPtr<IModelObject> spAssignmentValue;
        if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, 
                                                       &vtVal, 
                                                       &spAssignmentValue)))
        {
            ComPtr<IModelObject> spAssignmentResult;
            if (SUCCEEDED(spEval2->AssignTo(spIntValRef.Get(), 
                                            spAssignmentValue.Get(),
                                            &spAssignmentResult, 
                                            nullptr)))
            {
                // The (unsigned __int64)123456 was assigned to m_intVal with
                // the set of coercions defined by the language (C++)
                // spAssignmentResult has the language meaning of operator=() 
                // in this case.  This would be a MyClass&.
            }
        }
    }
}
```

## -see-also

[IDebugHostEvaluator2 interface](nn-dbgmodel-idebughostevaluator2.md)

