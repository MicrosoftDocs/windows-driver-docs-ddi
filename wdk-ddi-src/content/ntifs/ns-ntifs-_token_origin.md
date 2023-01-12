---
UID: NS:ntifs._TOKEN_ORIGIN
title: TOKEN_ORIGIN (ntifs.h)
description: The TOKEN_ORIGIN structure contains information about the origin of the logon session.
old-location: ifsk\token_origin.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_ORIGIN structure"]
ms.keywords: "*PTOKEN_ORIGIN, PTOKEN_ORIGIN, PTOKEN_ORIGIN structure pointer [Installable File System Drivers], TOKEN_ORIGIN, TOKEN_ORIGIN structure [Installable File System Drivers], _TOKEN_ORIGIN, ifsk.token_origin, ntifs/PTOKEN_ORIGIN, ntifs/TOKEN_ORIGIN, securitystructures_5cc2fc36-4e83-4544-8f24-dcbf768dbb9c.xml"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows Server 2003
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
req.typenames: TOKEN_ORIGIN, *PTOKEN_ORIGIN
f1_keywords:
 - _TOKEN_ORIGIN
 - ntifs/_TOKEN_ORIGIN
 - PTOKEN_ORIGIN
 - ntifs/PTOKEN_ORIGIN
 - TOKEN_ORIGIN
 - ntifs/TOKEN_ORIGIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_ORIGIN
 - PTOKEN_ORIGIN
 - TOKEN_ORIGIN
---

# TOKEN_ORIGIN structure

## -description

The **TOKEN_ORIGIN** structure contains information about the origin of the logon session.

## -struct-fields

### -field OriginatingLogonSession

The locally unique identifier (LUID) for the logon session. If the token resulted from a logon using explicit credentials, such as passing name, domain, and password to the user-mode **LogonUser** function, then this member will contain the ID of the logon session that created it. If the token resulted from network authentication, such as a call to the user-mode **AcceptSecurityContext**, or a call to the user-mode **LogonUser** function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this member will be zero.

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
