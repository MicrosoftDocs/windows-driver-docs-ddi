---
UID: NE:ntifs._TOKEN_TYPE
title: _TOKEN_TYPE (ntifs.h)
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["TOKEN_TYPE enumeration"]
ms.keywords: "*PTOKEN_TYPE, PTOKEN_TYPE, PTOKEN_TYPE enumeration pointer [Installable File System Drivers], TOKEN_TYPE, TOKEN_TYPE enumeration [Installable File System Drivers], TokenImpersonation, TokenPrimary, _TOKEN_TYPE, ifsk.token_type, ntifs/PTOKEN_TYPE, ntifs/TOKEN_TYPE, ntifs/TokenImpersonation, ntifs/TokenPrimary, securitystructures_b570f2e6-2426-4c9d-8552-81131cf4bd66.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: TOKEN_TYPE
f1_keywords:
 - _TOKEN_TYPE
 - ntifs/_TOKEN_TYPE
 - TOKEN_TYPE
 - ntifs/TOKEN_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_TYPE
 - TOKEN_TYPE
---

# _TOKEN_TYPE enumeration


## -description

The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.

## -enum-fields

### -field TokenPrimary

Indicates a primary token.

### -field TokenImpersonation

Indicates an impersonation token.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a>



<a href="/previous-versions/ff567102(v=vs.85)">ZwSetInformationToken</a>

