---
UID: NF:ntifs.SeTokenIsNoChildProcessRestrictionEnforced
title: SeTokenIsNoChildProcessRestrictionEnforced function (ntifs.h)
description: The SeTokenIsNoChildProcessRestrictionEnforced routine determines if the token carries the no child process restriction.
old-location: ifsk\setokenisnochildprocessrestrictionenforced.htm
tech.root: ifsk
ms.assetid: 6D214346-8CE6-4E9C-B054-1C72B928ED2B
ms.date: 04/16/2018
keywords: ["SeTokenIsNoChildProcessRestrictionEnforced function"]
ms.keywords: SeTokenIsNoChildProcessRestrictionEnforced, SeTokenIsNoChildProcessRestrictionEnforced function [Installable File System Drivers], ifsk.setokenisnochildprocessrestrictionenforced, ntifs/SeTokenIsNoChildProcessRestrictionEnforced
f1_keywords:
 - "ntifs/SeTokenIsNoChildProcessRestrictionEnforced"
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
- SeTokenIsNoChildProcessRestrictionEnforced
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeTokenIsNoChildProcessRestrictionEnforced function


## -description


The <b>SeTokenIsNoChildProcessRestrictionEnforced</b> routine determines if the token carries the no child process restriction.


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param UnlessSecure [out, optional]

Optionally provides a pointer to the value that will
        be set to TRUE when secure process creation is enabled even if
        process creation is restricted.


## -returns



This routine returns <b>TRUE</b> if <i>Token</i> carries the no child process restriction.



