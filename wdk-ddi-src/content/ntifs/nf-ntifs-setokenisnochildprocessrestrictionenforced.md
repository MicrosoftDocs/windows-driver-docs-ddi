---
UID: NF:ntifs.SeTokenIsNoChildProcessRestrictionEnforced
title: SeTokenIsNoChildProcessRestrictionEnforced function
author: windows-driver-content
description: The SeTokenIsNoChildProcessRestrictionEnforced routine determines if the token carries the no child process restriction.
old-location: ifsk\setokenisnochildprocessrestrictionenforced.htm
old-project: ifsk
ms.assetid: 6D214346-8CE6-4E9C-B054-1C72B928ED2B
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: SeTokenIsNoChildProcessRestrictionEnforced function [Installable File System Drivers], SeTokenIsNoChildProcessRestrictionEnforced, ifsk.setokenisnochildprocessrestrictionenforced, ntifs/SeTokenIsNoChildProcessRestrictionEnforced
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeTokenIsNoChildProcessRestrictionEnforced
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeTokenIsNoChildProcessRestrictionEnforced function


## -description


The <b>SeTokenIsNoChildProcessRestrictionEnforced</b> routine determines if the token carries the no child process restriction.


## -syntax


````
BOOLEAN NTKERNELAPI SeTokenIsNoChildProcessRestrictionEnforced(
  _In_      PACCESS_TOKEN Token,
  _Out_opt_ PBOOLEAN      UnlessSecure
);
````


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param UnlessSecure [out, optional]

Optionally provides a pointer to the value that will
        be set to TRUE when secure process creation is enabled even if
        process creation is restricted.


## -returns



This routine returns <b>TRUE</b> if <i>Token</i> carries the no child process restriction.



