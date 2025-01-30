---
UID: NF:dbgmodel.IDebugHostEvaluator3.AssignTo
tech.root: debugger
title: IDebugHostEvaluator3::AssignTo
ms.date: 01/20/2025
targetos: Windows
description: The AssignTo method performs assignment according to the semantics of the language being debugged.
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
 - IDebugHostEvaluator3::AssignTo
f1_keywords:
 - IDebugHostEvaluator3::AssignTo
 - dbgmodel/IDebugHostEvaluator3::AssignTo
dev_langs:
 - c++
helpviewer_keywords:
 - AssignTo
---

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

[IDebugHostEvaluator3 interface](nn-dbgmodel-idebughostevaluator3.md)