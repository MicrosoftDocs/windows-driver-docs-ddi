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


## -parameters




### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlCurrentOplock</b> returns <b>TRUE</b> if there are opportunistic locks (oplocks) that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FsRtlCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541950">FltCurrentOplock</a> instead of <b>FsRtlCurrentOplock</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541950">FltCurrentOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>
 

 

