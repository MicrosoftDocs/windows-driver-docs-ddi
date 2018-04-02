---
UID: NF:ntifs.SeAuditingFileOrGlobalEvents
title: SeAuditingFileOrGlobalEvents function
author: windows-driver-content
description: The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited.
old-location: ifsk\seauditingfileorglobalevents.htm
old-project: ifsk
ms.assetid: 4797126f-c27d-4951-88e7-37c5a475e77d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeAuditingFileOrGlobalEvents, SeAuditingFileOrGlobalEvents routine [Installable File System Drivers], ifsk.seauditingfileorglobalevents, ntifs/SeAuditingFileOrGlobalEvents, seref_06c1ee74-261c-4a57-b009-f76420e14055.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeAuditingFileOrGlobalEvents
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554770">SeAuditingFileEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556651">SeDeleteObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556682">SeOpenObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556685">SeOpenObjectForDeleteAuditAlarm</a>
 

 

