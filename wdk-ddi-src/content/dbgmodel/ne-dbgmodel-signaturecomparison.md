---
UID: NE:dbgmodel.SignatureComparison
title: SignatureComparison
author: windows-driver-content
description: Describes how a type or two signatures compare.
ms.assetid: 7157f5fb-4bdc-4380-aaef-882cb4c79993
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: SignatureComparison, , 
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	SignatureComparison
product: Windows
targetos: Windows
tech.root: debugger
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

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
