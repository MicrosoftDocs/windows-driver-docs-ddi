---
UID: NF:wdm.ExIsResourceAcquiredExclusiveLite
title: ExIsResourceAcquiredExclusiveLite function
author: windows-driver-content
description: The ExIsResourceAcquiredExclusiveLite routine returns whether the current thread has exclusive access to a given resource.
old-location: kernel\exisresourceacquiredexclusivelite.htm
old-project: kernel
ms.assetid: 81c07809-1c66-4b68-b2d9-05992c778ae6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.exisresourceacquiredexclusivelite, k102_ef023047-60ff-42aa-8224-37e2cfbe9f7b.xml, wdm/ExIsResourceAcquiredExclusiveLite, ExIsResourceAcquiredExclusiveLite, ExIsResourceAcquiredExclusiveLite routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExIsResourceAcquiredExclusiveLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExIsResourceAcquiredExclusiveLite function


## -description


The <b>ExIsResourceAcquiredExclusiveLite</b> routine returns whether the current thread has exclusive access to a given resource.


## -syntax


````
BOOLEAN ExIsResourceAcquiredExclusiveLite(
  _In_ PERESOURCE Resource
);
````


## -parameters




#### - Resource [in]

A pointer to the resource to be queried.


## -returns


<b>ExIsResourceAcquiredExclusiveLite</b> returns <b>TRUE</b> if the caller already has exclusive access to the given resource.



## -see-also

<a href="..\wdm\nf-wdm-exisresourceacquiredsharedlite.md">ExIsResourceAcquiredSharedLite</a>

<a href="..\wdm\nf-wdm-exacquireresourceexclusivelite.md">ExAcquireResourceExclusiveLite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExIsResourceAcquiredExclusiveLite routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

