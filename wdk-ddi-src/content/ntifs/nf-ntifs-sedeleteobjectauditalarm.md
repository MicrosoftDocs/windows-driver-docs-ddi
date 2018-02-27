---
UID: NF:ntifs.SeDeleteObjectAuditAlarm
title: SeDeleteObjectAuditAlarm function
author: windows-driver-content
description: The SeDeleteObjectAuditAlarm routine generates audit and alarm messages for an object that is marked for deletion.
old-location: ifsk\sedeleteobjectauditalarm.htm
old-project: ifsk
ms.assetid: 3d0a26e2-60d4-437e-b5cc-3ca7afee8f5a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeDeleteObjectAuditAlarm, SeDeleteObjectAuditAlarm routine [Installable File System Drivers], ifsk.sedeleteobjectauditalarm, ntifs/SeDeleteObjectAuditAlarm, seref_eb1715b3-9c8b-4848-8cc8-3809d0d35d9e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeDeleteObjectAuditAlarm
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeDeleteObjectAuditAlarm function


## -description


The <b>SeDeleteObjectAuditAlarm</b> routine generates audit and alarm messages for an object that is marked for deletion.


## -syntax


````
VOID SeDeleteObjectAuditAlarm(
  _In_ PVOID  Object,
  _In_ HANDLE Handle
);
````


## -parameters




### -param Object [in]

Address of the object.


### -param Handle [in]

A unique 32-bit value representing the client's handle to the object. 


## -returns



None




## -remarks



Callers of <b>SeDeleteObjectAuditAlarm</b> must have <b>SeAuditPrivilege</b> enabled. The test for this privilege is always performed against the primary token of the calling process, allowing the calling process to impersonate a client. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md">SeOpenObjectForDeleteAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-seauditingfileevents.md">SeAuditingFileEvents</a>



<a href="..\ntifs\nf-ntifs-seauditingfileorglobalevents.md">SeAuditingFileOrGlobalEvents</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeDeleteObjectAuditAlarm routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

