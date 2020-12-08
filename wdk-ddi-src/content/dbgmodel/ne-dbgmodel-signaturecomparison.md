---
UID: NE:dbgmodel.SignatureComparison
title: SignatureComparison (dbgmodel.h)
description: Describes how a type or two signatures compare.
ms.date: 07/16/2018
keywords: ["SignatureComparison enumeration"]
ms.keywords: SignatureComparison, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - SignatureComparison
 - dbgmodel/SignatureComparison
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - SignatureComparison
---

# SignatureComparison enumeration


## -description

Describes how a type or two signatures compare.

## -enum-fields

### -field Unrelated 

The two signatures/types being compared are unrelated.

### -field Ambiguous 

One signature/type compares ambiguously against the other.  For instance, std::pair<*, int> versus std::pair<int, *> are ambiguous.  There are types that would
 match both of these equally well (e.g.: std::pair<int, int>)

### -field LessSpecific 

One signature/type is less specific than the other.  For instance, a comparison of std::vector<*> against std::vector<int> would yield LessSpecific.

### -field MoreSpecific 

One signature/type is more specific than the other.  For instance, a comparison of std::vector<int> against std::vector<*> would yield MoreSpecific.

### -field Identical 

The signatures/types are identical.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
