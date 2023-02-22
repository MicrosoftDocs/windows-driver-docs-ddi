---
UID: NF:ntifs.SeAuditingFileOrGlobalEvents
title: SeAuditingFileOrGlobalEvents function (ntifs.h)
description: The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited.
old-location: ifsk\seauditingfileorglobalevents.htm
tech.root: ifsk
ms.date: 02/21/2023
keywords: ["SeAuditingFileOrGlobalEvents function"]
ms.keywords: SeAuditingFileOrGlobalEvents, SeAuditingFileOrGlobalEvents routine [Installable File System Drivers], ifsk.seauditingfileorglobalevents, ntifs/SeAuditingFileOrGlobalEvents, seref_06c1ee74-261c-4a57-b009-f76420e14055.xml
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeAuditingFileOrGlobalEvents
 - ntifs/SeAuditingFileOrGlobalEvents
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeAuditingFileOrGlobalEvents
---

# SeAuditingFileOrGlobalEvents function

## -description

The **SeAuditingFileOrGlobalEvents** routine determines whether file or global events are currently being audited.

## -parameters

### -param AccessGranted [in]

Set to TRUE if the access attempt was successful, FALSE otherwise.

### -param SecurityDescriptor [in]

Pointer to the security descriptor protecting the object being accessed.

### -param SubjectSecurityContext [in]

Pointer to the subject's captured security context.

## -returns

**SeAuditingFileOrGlobalEvents** returns TRUE if file or global events are currently being audited, FALSE otherwise.

## -remarks

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**SECURITY_DESCRIPTOR**](ns-ntifs-_security_descriptor.md)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)

[**SeAuditingFileEvents**](nf-ntifs-seauditingfileevents.md)

[**SeDeleteObjectAuditAlarm**](nf-ntifs-sedeleteobjectauditalarm.md)

[**SeOpenObjectAuditAlarm**](nf-ntifs-seopenobjectauditalarm.md)

[**SeOpenObjectForDeleteAuditAlarm**](nf-ntifs-seopenobjectfordeleteauditalarm.md)
