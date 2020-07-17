---
UID: NF:ntifs.SeAuditingFileOrGlobalEvents
title: SeAuditingFileOrGlobalEvents function (ntifs.h)
description: The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited.
old-location: ifsk\seauditingfileorglobalevents.htm
tech.root: ifsk
ms.assetid: 4797126f-c27d-4951-88e7-37c5a475e77d
ms.date: 04/16/2018
keywords: ["SeAuditingFileOrGlobalEvents function"]
ms.keywords: SeAuditingFileOrGlobalEvents, SeAuditingFileOrGlobalEvents routine [Installable File System Drivers], ifsk.seauditingfileorglobalevents, ntifs/SeAuditingFileOrGlobalEvents, seref_06c1ee74-261c-4a57-b009-f76420e14055.xml
f1_keywords:
 - "ntifs/SeAuditingFileOrGlobalEvents"
 - "SeAuditingFileOrGlobalEvents"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeAuditingFileOrGlobalEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeAuditingFileOrGlobalEvents function


## -description


The <b>SeAuditingFileOrGlobalEvents</b> routine determines whether file or global events are currently being audited.


## -parameters




### -param AccessGranted [in]

Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.


### -param SecurityDescriptor [in]

Pointer to the security descriptor protecting the object being accessed. 


### -param SubjectSecurityContext [in]

Pointer to the subject's captured security context.


## -returns



<b>SeAuditingFileOrGlobalEvents</b> returns <b>TRUE</b> if file or global events are currently being audited, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileevents">SeAuditingFileEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sedeleteobjectauditalarm">SeDeleteObjectAuditAlarm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectauditalarm">SeOpenObjectAuditAlarm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectfordeleteauditalarm">SeOpenObjectForDeleteAuditAlarm</a>
 

 

