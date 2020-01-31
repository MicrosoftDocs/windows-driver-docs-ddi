---
UID: NF:ntifs.SeTokenGetNoChildProcessRestricted
title: SeTokenGetNoChildProcessRestricted function (ntifs.h)
description: The SeTokenGetNoChildProcessRestricted routine determines the state of the no child process mitigation. It is not possible to be enforced and audit-only at the same time.
old-location: ifsk\setokengetnochildprocessrestricted.htm
tech.root: ifsk
ms.assetid: 6C42E6C4-91EB-44A3-84E1-CAFDBD5CD724
ms.date: 04/16/2018
ms.keywords: SeTokenGetNoChildProcessRestricted, SeTokenGetNoChildProcessRestricted function [Installable File System Drivers], ifsk.setokengetnochildprocessrestricted, ntifs/SeTokenGetNoChildProcessRestricted
f1_keywords:
 - "ntifs/SeTokenGetNoChildProcessRestricted"
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
- SeTokenGetNoChildProcessRestricted
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeTokenGetNoChildProcessRestricted function


## -description


The <b>SeTokenGetNoChildProcessRestricted</b> routine determines the state of the no child process mitigation.  It is
    not possible to be enforced and audit-only at the same time.


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param Enforced [out]

A pointer to a boolean that returns whether the mitigation is in enforcement mode.


### -param UnlessSecure [out]

A pointer to a boolean that returns whether secure process creation is enabled even if
        process creation is restricted.


### -param AuditOnly [out]

A pointer to a boolean that returns whether the mitigation is in audit-only mode.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokensetnochildprocessrestricted">SeTokenSetNoChildProcessRestricted</a>
 

 

