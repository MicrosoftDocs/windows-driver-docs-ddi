---
UID: NF:ntifs.SeAuditingFileEvents
title: SeAuditingFileEvents function
author: windows-driver-content
description: The SeAuditingFileEvents routine determines whether file open events are currently being audited.
old-location: ifsk\seauditingfileevents.htm
old-project: ifsk
ms.assetid: f9e9a53f-9f4a-4f44-befa-f11d1fb3372a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, E, F, S, SeAuditingFileEvents, SeAuditingFileEvents routine [Installable File System Drivers], d, e, g, i, ifsk.seauditingfileevents, l, n, ntifs/SeAuditingFileEvents, s, seref_b4b8468e-cfb2-4685-9811-2b2733e9fb36.xml, t, u, v"
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
-	SeAuditingFileEvents
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeAuditingFileEvents function


## -description


The <b>SeAuditingFileEvents</b> routine determines whether file open events are currently being audited.


## -syntax


````
BOOLEAN SeAuditingFileEvents(
  _In_ BOOLEAN              AccessGranted,
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters




### -param AccessGranted [in]

Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.


### -param SecurityDescriptor [in]

This parameter is ignored.


## -returns



<b>SeAuditingFileEvents</b> returns <b>TRUE</b> if file open events are currently being audited, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md">SeOpenObjectForDeleteAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-seauditingfileorglobalevents.md">SeAuditingFileOrGlobalEvents</a>



<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-sedeleteobjectauditalarm.md">SeDeleteObjectAuditAlarm</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeAuditingFileEvents routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

