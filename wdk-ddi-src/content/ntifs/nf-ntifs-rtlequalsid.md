---
UID: NF:ntifs.RtlEqualSid
title: RtlEqualSid function (ntifs.h)
description: The RtlEqualSid routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.
old-location: ifsk\rtlequalsid.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlEqualSid function"]
ms.keywords: RtlEqualSid, RtlEqualSid routine [Installable File System Drivers], ifsk.rtlequalsid, ntifs/RtlEqualSid, rtlref_bc81c0ad-e0e6-4133-a423-4f6c4c264286.xml
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEqualSid
 - ntifs/RtlEqualSid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlEqualSid
---

# RtlEqualSid function


## -description

The <b>RtlEqualSid</b> routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.

## -parameters

### -param Sid1 

[in]
Pointer to the first SID structure to compare. Must point to a valid SID.

### -param Sid2 

[in]
Pointer to the second SID structure to compare. Must point to a valid SID.

## -returns

<b>RtlEqualSid</b> returns <b>TRUE</b> if the SID structures are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined.

## -remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcopysid">RtlCopySid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalprefixsid">RtlEqualPrefixSid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlvalidsid">RtlValidSid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
