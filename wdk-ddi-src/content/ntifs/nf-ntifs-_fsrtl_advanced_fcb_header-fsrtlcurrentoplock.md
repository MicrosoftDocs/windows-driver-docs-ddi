---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCurrentOplock
title: FsRtlCurrentOplock function
author: windows-driver-content
description: A file system or filter driver calls FsRtlCurrentOplock to determine whether there are any opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentoplock.htm
old-project: ifsk
ms.assetid: b7cf8765-6f24-4b65-9171-6bfad7214013
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlCurrentOplock, FsRtlCurrentOplock function [Installable File System Drivers], fsrtlref_3caa67c9-324a-4694-95a3-f84105055b48.xml, ifsk.fsrtlcurrentoplock, ntifs/FsRtlCurrentOplock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCurrentOplock routine is available starting with Windows Vista.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlCurrentOplock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlCurrentOplock function


## -description


A file system or filter driver calls <b>FsRtlCurrentOplock</b> to determine whether there are any opportunistic locks (oplocks) on a file. 


## -syntax


````
BOOLEAN FsRtlCurrentOplock(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlCurrentOplock</b> returns <b>TRUE</b> if there are opportunistic locks (oplocks) that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FsRtlCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltcurrentoplock.md">FltCurrentOplock</a> instead of <b>FsRtlCurrentOplock</b>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcurrentoplock.md">FltCurrentOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCurrentOplock function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

