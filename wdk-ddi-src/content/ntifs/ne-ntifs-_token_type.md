---
UID: NE:ntifs._TOKEN_TYPE
title: _TOKEN_TYPE (ntifs.h)
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
tech.root: ifsk
ms.assetid: 2ad78d17-9baa-45cf-a620-01c2ccd14338
ms.date: 04/16/2018
ms.keywords: "*PTOKEN_TYPE, PTOKEN_TYPE, PTOKEN_TYPE enumeration pointer [Installable File System Drivers], TOKEN_TYPE, TOKEN_TYPE enumeration [Installable File System Drivers], TokenImpersonation, TokenPrimary, _TOKEN_TYPE, ifsk.token_type, ntifs/PTOKEN_TYPE, ntifs/TOKEN_TYPE, ntifs/TokenImpersonation, ntifs/TokenPrimary, securitystructures_b570f2e6-2426-4c9d-8552-81131cf4bd66.xml"
ms.topic: enum
f1_keywords:
 - "ntifs/TOKEN_TYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- TOKEN_TYPE
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

