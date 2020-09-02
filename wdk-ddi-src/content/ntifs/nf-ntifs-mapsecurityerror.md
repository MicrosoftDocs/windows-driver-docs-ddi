---
UID: NF:ntifs.MapSecurityError
title: MapSecurityError function (ntifs.h)
description: The MapSecurityError function maps a security interface SECURITY_STATUS status code to a corresponding NSTATUS status code.
old-location: ifsk\mapsecurityerror.htm
tech.root: ifsk
ms.assetid: 899b7d6e-a17b-4030-9512-591b003ca6b2
ms.date: 04/16/2018
keywords: ["MapSecurityError function"]
ms.keywords: IFSMiscRef_41a163d7-81d1-4877-b1c2-ae90b203177a.xml, MapSecurityError, MapSecurityError function [Installable File System Drivers], ifsk.mapsecurityerror, ntifs/MapSecurityError
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.irql: Any.
targetos: Windows
req.typenames: 
f1_keywords:
 - MapSecurityError
 - ntifs/MapSecurityError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MapSecurityError
---

# MapSecurityError function


## -description

The <b>MapSecurityError</b> function maps a security interface SECURITY_STATUS status code to a corresponding NSTATUS status code.

## -parameters

### -param SecStatus

<p>The security interface SECURITY_STATUS status code to be mapped.</p>

## -returns

The NTSTATUS status code corresponding to the input Error status code.

## -remarks

This function maps a security interface status code of type SECURITY_STATUS to a corresponding NSTATUS status code.

