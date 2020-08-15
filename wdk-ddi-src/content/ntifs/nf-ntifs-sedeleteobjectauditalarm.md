---
UID: NF:ntifs.SeDeleteObjectAuditAlarm
title: SeDeleteObjectAuditAlarm function (ntifs.h)
description: The SeDeleteObjectAuditAlarm routine generates audit and alarm messages for an object that is marked for deletion.
old-location: ifsk\sedeleteobjectauditalarm.htm
tech.root: ifsk
ms.assetid: 3d0a26e2-60d4-437e-b5cc-3ca7afee8f5a
ms.date: 04/16/2018
keywords: ["SeDeleteObjectAuditAlarm function"]
ms.keywords: SeDeleteObjectAuditAlarm, SeDeleteObjectAuditAlarm routine [Installable File System Drivers], ifsk.sedeleteobjectauditalarm, ntifs/SeDeleteObjectAuditAlarm, seref_eb1715b3-9c8b-4848-8cc8-3809d0d35d9e.xml
f1_keywords:
 - "ntifs/SeDeleteObjectAuditAlarm"
 - "SeDeleteObjectAuditAlarm"
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
- SeDeleteObjectAuditAlarm
targetos: Windows
req.typenames: 
---

# SeDeleteObjectAuditAlarm function


## -description


The <b>SeDeleteObjectAuditAlarm</b> routine generates audit and alarm messages for an object that is marked for deletion.


## -parameters




### -param Object 
[in]
Address of the object.


### -param Handle 
[in]
A unique 32-bit value representing the client's handle to the object. 


## -remarks



Callers of <b>SeDeleteObjectAuditAlarm</b> must have <b>SeAuditPrivilege</b> enabled. The test for this privilege is always performed against the primary token of the calling process, allowing the calling process to impersonate a client. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileevents">SeAuditingFileEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileorglobalevents">SeAuditingFileOrGlobalEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectauditalarm">SeOpenObjectAuditAlarm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectfordeleteauditalarm">SeOpenObjectForDeleteAuditAlarm</a>
 

 

