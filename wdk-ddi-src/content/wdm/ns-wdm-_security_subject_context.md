---
UID: NS:wdm._SECURITY_SUBJECT_CONTEXT
title: SECURITY_SUBJECT_CONTEXT (wdm.h)
description: The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing.
old-location: ifsk\security_subject_context.htm
tech.root: ifsk
ms.date: 02/13/2023
keywords: ["SECURITY_SUBJECT_CONTEXT structure"]
ms.keywords: "*PSECURITY_SUBJECT_CONTEXT, PSECURITY_SUBJECT_CONTEXT, PSECURITY_SUBJECT_CONTEXT structure pointer [Installable File System Drivers], SECURITY_SUBJECT_CONTEXT, SECURITY_SUBJECT_CONTEXT structure [Installable File System Drivers], _SECURITY_SUBJECT_CONTEXT, ifsk.security_subject_context, securitystructures_e91a762f-82dc-4319-a479-8de15bce2bfd.xml, wdm/PSECURITY_SUBJECT_CONTEXT, wdm/SECURITY_SUBJECT_CONTEXT"
req.header: wdm.h
req.include-header: Wdm.h
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
req.typenames: SECURITY_SUBJECT_CONTEXT, *PSECURITY_SUBJECT_CONTEXT
f1_keywords:
 - _SECURITY_SUBJECT_CONTEXT
 - wdm/_SECURITY_SUBJECT_CONTEXT
 - PSECURITY_SUBJECT_CONTEXT
 - wdm/PSECURITY_SUBJECT_CONTEXT
 - SECURITY_SUBJECT_CONTEXT
 - wdm/SECURITY_SUBJECT_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _SECURITY_SUBJECT_CONTEXT
 - PSECURITY_SUBJECT_CONTEXT
 - SECURITY_SUBJECT_CONTEXT
---

# SECURITY_SUBJECT_CONTEXT structure

## -description

The **SECURITY_SUBJECT_CONTEXT** structure is used to capture subject security context for access validation and auditing.

*Drivers must not modify or try to directly access any members of this structure to make security decisions. To create and manipulate this structure, use the support routines listed in the **See Also** section.*

## -struct-fields

### -field ClientToken

Reserved for system use.

### -field ImpersonationLevel

Reserved for system use.

### -field PrimaryToken

Reserved for system use.

### -field ProcessAuditId

Reserved for system use.

## -remarks

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**ACCESS_STATE**](ns-wdm-_access_state.md)

[**FsRtlNotifyFullChangeDirectory**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory.md)

[**SECURITY_IMPERSONATION_LEVEL**](ne-wdm-_security_impersonation_level.md)

[**SeAccessCheck**](nf-wdm-seaccesscheck.md)

[**SeAssignSecurity**](nf-wdm-seassignsecurity.md)

[**SeAssignSecurityEx**](nf-wdm-seassignsecurityex.md)

[**SeAuditingFileOrGlobalEvents**](../ntifs/nf-ntifs-seauditingfileorglobalevents.md)

[**SeCaptureSubjectContext**](../ntifs/nf-ntifs-secapturesubjectcontext.md)

[**SeCreateClientSecurityFromSubjectContext**](../ntifs/nf-ntifs-secreateclientsecurityfromsubjectcontext.md)

[**SeFilterToken**](../ntifs/nf-ntifs-sefiltertoken.md)

[**SeLockSubjectContext**](../ntifs/nf-ntifs-selocksubjectcontext.md)

[**SePrivilegeCheck**](../ntifs/nf-ntifs-seprivilegecheck.md)

[**SeQuerySubjectContextToken**](../ntifs/nf-ntifs-sequerysubjectcontexttoken.md)

[**SeReleaseSubjectContext**](../ntifs/nf-ntifs-sereleasesubjectcontext.md)

[**SeUnlockSubjectContext**](../ntifs/nf-ntifs-seunlocksubjectcontext.md)
