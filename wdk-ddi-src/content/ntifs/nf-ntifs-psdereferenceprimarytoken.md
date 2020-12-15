---
UID: NF:ntifs.PsDereferencePrimaryToken
title: PsDereferencePrimaryToken function (ntifs.h)
description: The PsDereferencePrimaryToken routine decrements the reference count of a primary token.
old-location: ifsk\psdereferenceprimarytoken.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PsDereferencePrimaryToken function"]
ms.keywords: PsDereferencePrimaryToken, PsDereferencePrimaryToken routine [Installable File System Drivers], ifsk.psdereferenceprimarytoken, ntifs/PsDereferencePrimaryToken, psref_d3e4caeb-19a5-49d5-909a-5cb78a54f2e5.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsDereferencePrimaryToken
 - ntifs/PsDereferencePrimaryToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsDereferencePrimaryToken
---

# PsDereferencePrimaryToken function


## -description

The <b>PsDereferencePrimaryToken</b> routine decrements the reference count of a primary token.

## -parameters

### -param PrimaryToken 

[in]
Pointer to the primary token whose reference count is to be decremented.

## -remarks

If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceimpersonationtoken">PsDereferenceImpersonationToken</a>
