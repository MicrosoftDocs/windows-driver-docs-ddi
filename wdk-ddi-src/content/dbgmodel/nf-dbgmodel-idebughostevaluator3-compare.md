---
UID: NF:dbgmodel.IDebugHostEvaluator3.Compare
tech.root: debugger
title: IDebugHostEvaluator3::Compare
ms.date: 01/20/2025
targetos: Windows
description: The Compare method compares two model-based objects for equality linguistically. It handles pointers and pointer coercion equality if necessary.
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
 - IDebugHostEvaluator3::Compare
f1_keywords:
 - IDebugHostEvaluator3::Compare
 - dbgmodel/IDebugHostEvaluator3::Compare
dev_langs:
 - c++
helpviewer_keywords:
 - Compare
---

## -description

The Compare method compares two model-based objects for equality linguistically. It handles pointers and pointer coercion equality if necessary.

## -parameters

### -param pLeft

A pointer to the [IModelObject interface](nn-dbgmodel-imodelobject.md) of the first object to be compared.

### -param pRight

A pointer to the [IModelObject interface](nn-dbgmodel-imodelobject.md) of the second object to be compared.

### -param ppResult

A pointer to a pointer variable that receives the result [IModelObject interface](nn-dbgmodel-imodelobject.md). This will contain the result of the comparison.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

The Compare method is useful for linguistic and semantic comparisons of model-based objects, including checks for pointer and pointer coercion equality.

## -see-also

[IDebugHostEvaluator3 interface](nn-dbgmodel-idebughostevaluator3.md)