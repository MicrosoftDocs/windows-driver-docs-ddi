---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDeleteKeyFromTunnelCache~r1
title: FsRtlDeleteKeyFromTunnelCache function
author: windows-driver-content
description: The FsRtlDeleteKeyFromTunnelCache routine deletes any tunnel cache entries for files in a directory that is being deleted.
old-location: ifsk\fsrtldeletekeyfromtunnelcache.htm
old-project: ifsk
ms.assetid: 01f0d1ab-7c7f-4ee2-89f0-c48b257bafbb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlDeleteKeyFromTunnelCache, FsRtlDeleteKeyFromTunnelCache routine [Installable File System Drivers], fsrtlref_cbb2d1c7-d4c5-4fe0-9e35-d09dac0e7eff.xml, ifsk.fsrtldeletekeyfromtunnelcache, ntifs/FsRtlDeleteKeyFromTunnelCache
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlDeleteKeyFromTunnelCache
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDeleteKeyFromTunnelCache function


## -description


The <b>FsRtlDeleteKeyFromTunnelCache</b> routine deletes any tunnel cache entries for files in a directory that is being deleted.


## -parameters




### -param Cache [in]

A pointer to a tunnel cache that was initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546153">FsRtlInitializeTunnelCache</a>.


### -param DirectoryKey

TBD




#### - DirKey [in]

The directory key value for the directory that is being removed. For more information, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff546153">FsRtlInitializeTunnelCache</a>.


## -returns



None




## -remarks



File systems call <b>FsRtlDeleteKeyFromTunnelCache</b> when deleting a directory from a volume. <b>FsRtlDeleteKeyFromTunnelCache</b> deletes all tunnel cache entries whose directory keys match the value specified in the <i>DirKey</i> parameter. 

To delete the tunnel cache, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545863">FsRtlDeleteTunnelCache</a>.

The caller is required to synchronize this call against <a href="https://msdn.microsoft.com/library/windows/hardware/ff545863">FsRtlDeleteTunnelCache</a>. In other words, a file system must ensure that it does not call <b>FsRtlDeleteKeyFromTunnelCache</b> and <b>FsRtlDeleteTunnelCache</b> at the same time from different threads. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545863">FsRtlDeleteTunnelCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546153">FsRtlInitializeTunnelCache</a>
 

 

