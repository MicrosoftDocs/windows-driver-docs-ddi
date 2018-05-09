---
UID: NF:ntifs.SeTokenSetNoChildProcessRestricted
title: SeTokenSetNoChildProcessRestricted function
author: windows-driver-content
description: The SeTokenSetNoChildProcessRestricted routine sets the TOKEN_AUDIT_NO_CHILD_PROCESS or TOKEN_AUDIT_NO_CHILD_PROCESS flags in the token.
old-location: ifsk\setokensetnochildprocessrestricted.htm
old-project: ifsk
ms.assetid: FCFCBF4C-CBAA-4284-A6F4-67630608CF19
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: SeTokenSetNoChildProcessRestricted, SeTokenSetNoChildProcessRestricted function [Installable File System Drivers], ifsk.setokensetnochildprocessrestricted, ntifs/SeTokenSetNoChildProcessRestricted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeTokenSetNoChildProcessRestricted
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeTokenSetNoChildProcessRestricted function


## -description


The <b>SeTokenSetNoChildProcessRestricted</b> routine sets the <b>TOKEN_AUDIT_NO_CHILD_PROCESS</b> or <b>TOKEN_AUDIT_NO_CHILD_PROCESS</b>
    flags in the token.  


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param UnlessSecure [in]

A pointer to a boolean that indicates that secure process creation shoudl always be enabled.


### -param AuditOnly [in]

A pointer to a boolean that indicates if the mitigation should be enabled in
                audit-only mode.


## -returns



This function does not return a value.




## -remarks



Note that both flags cannot be set at the same time
    and it is possible to upgrade from audit-only mode to enforcement
    mode but not vice-versa.




## -see-also




<a href="https://msdn.microsoft.com/6C42E6C4-91EB-44A3-84E1-CAFDBD5CD724">SeTokenGetNoChildProcessRestricted</a>
 

 

