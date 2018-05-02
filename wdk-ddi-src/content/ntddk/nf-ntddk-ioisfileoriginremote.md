---
UID: NF:ntddk.IoIsFileOriginRemote
title: IoIsFileOriginRemote function
author: windows-driver-content
description: The IoIsFileOriginRemote routine determines whether a given file object is for a remote create request.
old-location: ifsk\ioisfileoriginremote.htm
old-project: ifsk
ms.assetid: 46655cbe-0483-4897-bd12-ce108af326c6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IoIsFileOriginRemote, IoIsFileOriginRemote routine [Installable File System Drivers], ifsk.ioisfileoriginremote, ioref_04dab537-9cd7-44be-9592-0682c0bfbd7e.xml, ntddk/IoIsFileOriginRemote
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoIsFileOriginRemote
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoIsFileOriginRemote function


## -description


The <b>IoIsFileOriginRemote</b> routine determines whether a given file object is for a remote create request. 


## -parameters




### -param FileObject [in]

Pointer to a file object for the file. 


## -returns



<b>IoIsFileOriginRemote</b> returns <b>TRUE</b> if the file object was created to satisfy a remote create request, otherwise <b>FALSE</b>. 




## -remarks



File system filter drivers call <b>IoIsFileOriginRemote</b> for a file object to determine whether it represents a remote create request. 

<b>IoIsFileOriginRemote</b> must be called after the create request has entirely completed. In other words, it cannot be called in the create dispatch ("pre-create") path or the create completion ("post-create") path. 

<b>IoIsFileOriginRemote</b> checks the FO_REMOTE_ORIGIN flag on the file object pointed to by <i>FileObject</i>. Network file systems set or clear this flag by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548535">IoSetFileOrigin</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548535">IoSetFileOrigin</a>
 

 

