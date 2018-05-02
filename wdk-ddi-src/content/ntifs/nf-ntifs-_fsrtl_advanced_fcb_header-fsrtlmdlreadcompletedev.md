---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadCompleteDev
title: FsRtlMdlReadCompleteDev function
author: windows-driver-content
description: The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated.
old-location: ifsk\fltfastiomdlreadcomplete.htm
old-project: ifsk
ms.assetid: 6F5E808C-9E35-4BE8-AE67-FDD354D6FD0E
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltFastIoMdlReadComplete, FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadCompleteDev, ifsk.fltfastiomdlreadcomplete
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
-	FsRtlMdlReadCompleteDev
product: Windows
targetos: Windows
req.typenames: 
---

# FsRtlMdlReadCompleteDev function


## -description


The <b>FltFastIoMdlReadComplete</b> routine completes the read operation that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706188">FltFastIoMdlRead</a> routine initiated.


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param MdlChain [in]

On return, a pointer to a linked list of one or more MDLs that point to the cached file data.


### -param DeviceObject

TBD




#### - InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None




## -remarks



The <b>FltFastIoMdlReadComplete</b> routine unlocks the pages in cache memory that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706188">FltFastIoMdlRead</a> routine allocated.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh706188">FltFastIoMdlRead</a>
 

 

