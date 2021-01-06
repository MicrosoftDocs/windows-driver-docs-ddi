---
UID: NF:ntifs.SeAuditingFileEvents
title: SeAuditingFileEvents function (ntifs.h)
description: The SeAuditingFileEvents routine determines whether file open events are currently being audited.
old-location: ifsk\seauditingfileevents.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["SeAuditingFileEvents function"]
ms.keywords: SeAuditingFileEvents, SeAuditingFileEvents routine [Installable File System Drivers], ifsk.seauditingfileevents, ntifs/SeAuditingFileEvents, seref_b4b8468e-cfb2-4685-9811-2b2733e9fb36.xml
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
 - SeAuditingFileEvents
 - ntifs/SeAuditingFileEvents
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeAuditingFileEvents
---

# SeAuditingFileEvents function


## -description

The <b>SeAuditingFileEvents</b> routine determines whether file open events are currently being audited.

## -parameters

### -param AccessGranted 

[in]
Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.

### -param SecurityDescriptor 

[in]
This parameter is ignored.

## -returns

<b>SeAuditingFileEvents</b> returns <b>TRUE</b> if file open events are currently being audited, <b>FALSE</b> otherwise.

## -remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileorglobalevents">SeAuditingFileOrGlobalEvents</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sedeleteobjectauditalarm">SeDeleteObjectAuditAlarm</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectauditalarm">SeOpenObjectAuditAlarm</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectfordeleteauditalarm">SeOpenObjectForDeleteAuditAlarm</a>
