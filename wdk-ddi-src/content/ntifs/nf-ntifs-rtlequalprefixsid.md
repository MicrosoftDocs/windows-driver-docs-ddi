---
UID: NF:ntifs.RtlEqualPrefixSid
title: RtlEqualPrefixSid function (ntifs.h)
description: The RtlEqualPrefixSid routine determines whether two security-identifier (SID) prefixes are equal. An SID prefix is the entire SID except for the last subauthority value.
old-location: ifsk\rtlequalprefixsid.htm
tech.root: ifsk
ms.assetid: 6db96d3b-721f-40d5-8f8d-54cdd33f85c8
ms.date: 04/16/2018
keywords: ["RtlEqualPrefixSid function"]
ms.keywords: RtlEqualPrefixSid, RtlEqualPrefixSid routine [Installable File System Drivers], ifsk.rtlequalprefixsid, ntifs/RtlEqualPrefixSid, rtlref_67b0c7e1-647f-426a-8d9d-dde2d98b0cc3.xml
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
req.lib: Ntdll.lib
req.dll: Ntdll.dll
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEqualPrefixSid
 - ntifs/RtlEqualPrefixSid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntdll.dll
api_name:
 - RtlEqualPrefixSid
---

# RtlEqualPrefixSid function


## -description

The <b>RtlEqualPrefixSid</b> routine determines whether two security-identifier (SID) prefixes are equal. An SID prefix is the entire SID except for the last subauthority value.

## -parameters

### -param Sid1 

[in]
Pointer to the first SID structure to compare. Must point to a valid SID.

### -param Sid2 

[in]
Pointer to the second SID structure to compare. Must point to a valid SID.

## -returns

<b>RtlEqualPrefixSid</b> returns <b>TRUE</b> if the SID prefixes are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined.

## -remarks

<b>RtlEqualPrefixSid</b> enables a server in one domain to verify an attempt by a user to log on to another domain. For example, if a user attempts to log on to RemoteDomain from a workstation in LocalDomain, the server for LocalDomain can request the SIDs for the user and the user's groups from RemoteDomain. The domain controller for RemoteDomain responds with the relevant SIDs. 

All SIDs for a specified domain necessarily have the same prefix. When the server receives the user's SIDs, it can call <b>RtlEqualPrefixSid</b> for each SID, comparing the user or group SID against the SID for RemoteDomain. If any of the SID prefixes are not equal, the server refuses the logon attempt. 

It is advisable to modify the SID for a domain before comparing it with a group or user SID. If the SID for RemoteDomain is S-1-1234-8, each group or user SID for that domain will have S-1-1234-8 as its prefix. To compare the SIDs by using <b>RtlEqualPrefixSid</b>, the caller copies the domain SID and adds any subauthority relative identifier value to the copy, thereby creating an SID in the form S-1-1234-8-0. (The relative identifier, or RID, is the portion of a SID that identifies a user or group in relation to the authority that issued the SID.) The caller then uses the modified domain SID as a template against which the group and user SIDs are compared. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcopysid">RtlCopySid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalsid">RtlEqualSid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlvalidsid">RtlValidSid</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>