---
UID: NF:ntifs.SeTokenSetNoChildProcessRestricted
title: SeTokenSetNoChildProcessRestricted function (ntifs.h)
description: The SeTokenSetNoChildProcessRestricted routine sets the TOKEN_AUDIT_NO_CHILD_PROCESS or TOKEN_AUDIT_NO_CHILD_PROCESS flags in the token.
old-location: ifsk\setokensetnochildprocessrestricted.htm
tech.root: ifsk
ms.assetid: FCFCBF4C-CBAA-4284-A6F4-67630608CF19
ms.date: 04/16/2018
keywords: ["SeTokenSetNoChildProcessRestricted function"]
ms.keywords: SeTokenSetNoChildProcessRestricted, SeTokenSetNoChildProcessRestricted function [Installable File System Drivers], ifsk.setokensetnochildprocessrestricted, ntifs/SeTokenSetNoChildProcessRestricted
f1_keywords:
 - "ntifs/SeTokenSetNoChildProcessRestricted"
 - "SeTokenSetNoChildProcessRestricted"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeTokenSetNoChildProcessRestricted
targetos: Windows
req.typenames: 
---

# SeTokenSetNoChildProcessRestricted function


## -description


The <b>SeTokenSetNoChildProcessRestricted</b> routine sets the <b>TOKEN_NO_CHILD_PROCESS_UNLESS_SECURE</b> or <b>TOKEN_AUDIT_NO_CHILD_PROCESS</b>
    flags in the token.  


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param UnlessSecure [in]

A pointer to a boolean that indicates that secure process creation should always be enabled.


### -param AuditOnly [in]

A pointer to a boolean that indicates if the mitigation should be enabled in
                audit-only mode.


## -remarks



Note that both flags cannot be set at the same time
    and it is possible to upgrade from audit-only mode to enforcement
    mode but not vice-versa.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokengetnochildprocessrestricted">SeTokenGetNoChildProcessRestricted</a>
 

 

