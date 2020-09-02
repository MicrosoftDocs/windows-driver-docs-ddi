---
UID: NS:ntifs._SID
title: _SID (ntifs.h)
description: The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.
old-location: ifsk\sid.htm
tech.root: ifsk
ms.assetid: 3b0d68f9-e871-42fe-97b0-f70f1fa72bf0
ms.date: 04/16/2018
keywords: ["SID structure"]
ms.keywords: "*PISID, PSID, PSID structure pointer [Installable File System Drivers], SID, SID structure [Installable File System Drivers], _SID, ifsk.sid, ntifs/PSID, ntifs/SID, securitystructures_748be9da-f428-42cd-a1f8-eca090e2b3aa.xml"
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
targetos: Windows
req.typenames: SID, *PISID
f1_keywords:
 - _SID
 - ntifs/_SID
 - PISID
 - ntifs/PISID
 - SID
 - ntifs/SID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SID
---

# _SID structure


## -description

The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.

Drivers are not to modify the SID structure directly. To create and manipulate a security identifier, use the support routines listed in the See Also section.

## -struct-fields

### -field Revision

### -field SubAuthorityCount

### -field IdentifierAuthority

### -field SubAuthority.size_is

### -field SubAuthority.size_is.SubAuthorityCount

### -field SubAuthority

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcopysid">RtlCopySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalprefixsid">RtlEqualPrefixSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalsid">RtlEqualSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetownersecuritydescriptor">RtlGetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializesid">RtlInitializeSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtllengthsid">RtlLengthSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsubauthoritysid">RtlSubAuthoritySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlvalidsid">RtlValidSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a>

