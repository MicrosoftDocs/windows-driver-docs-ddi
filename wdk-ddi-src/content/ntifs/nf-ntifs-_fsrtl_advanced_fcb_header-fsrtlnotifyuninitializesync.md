---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyUninitializeSync
title: FsRtlNotifyUninitializeSync function
author: windows-driver-content
description: The FsRtlNotifyUninitializeSync routine deallocates the synchronization object for a notify list.
old-location: ifsk\fsrtlnotifyuninitializesync.htm
old-project: ifsk
ms.assetid: ac26d5cb-b342-42ec-ad76-23cefe509566
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fsrtlref_bb1d0439-691c-4a2d-8d0f-750f26d75995.xml, FsRtlNotifyUninitializeSync, ifsk.fsrtlnotifyuninitializesync, ntifs/FsRtlNotifyUninitializeSync, FsRtlNotifyUninitializeSync routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlNotifyUninitializeSync
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyUninitializeSync function


## -description


The <b>FsRtlNotifyUninitializeSync</b> routine deallocates the synchronization object for a notify list.


## -syntax


````
VOID FsRtlNotifyUninitializeSync(
  _In_ PNOTIFY_SYNC *NotifySync
);
````


## -parameters




### -param NotifySync [in]

A pointer to a location that contains a pointer to the opaque synchronization object.


## -returns



None




## -remarks



The <b>FsRtlNotifyUninitializeSync</b> routine deallocates an opaque synchronization object that was allocated by an earlier call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync.md">FsRtlNotifyInitializeSync</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync.md">FsRtlNotifyInitializeSync</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNotifyUninitializeSync routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

