---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDeleteKeyFromTunnelCache
title: FsRtlDeleteKeyFromTunnelCache function (ntifs.h)
description: The FsRtlDeleteKeyFromTunnelCache routine deletes any tunnel cache entries for files in a directory that is being deleted.
old-location: ifsk\fsrtldeletekeyfromtunnelcache.htm
tech.root: ifsk
ms.assetid: 01f0d1ab-7c7f-4ee2-89f0-c48b257bafbb
ms.date: 04/16/2018
ms.keywords: FsRtlDeleteKeyFromTunnelCache, FsRtlDeleteKeyFromTunnelCache routine [Installable File System Drivers], fsrtlref_cbb2d1c7-d4c5-4fe0-9e35-d09dac0e7eff.xml, ifsk.fsrtldeletekeyfromtunnelcache, ntifs/FsRtlDeleteKeyFromTunnelCache
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlDeleteKeyFromTunnelCache
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlDeleteKeyFromTunnelCache function


## -description


The <b>FsRtlDeleteKeyFromTunnelCache</b> routine deletes any tunnel cache entries for files in a directory that is being deleted.


## -parameters




### -param Cache [in]

A pointer to a tunnel cache that was initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache">FsRtlInitializeTunnelCache</a>.


### -param DirectoryKey

<p>The directory key value for the directory that is being removed. For more information, see the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache"><b>FsRtlInitializeTunnelCache</b></a>.</p>




## -returns



None




## -remarks



File systems call <b>FsRtlDeleteKeyFromTunnelCache</b> when deleting a directory from a volume. <b>FsRtlDeleteKeyFromTunnelCache</b> deletes all tunnel cache entries whose directory keys match the value specified in the <i>DirKey</i> parameter. 

To delete the tunnel cache, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache">FsRtlDeleteTunnelCache</a>.

The caller is required to synchronize this call against <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache">FsRtlDeleteTunnelCache</a>. In other words, a file system must ensure that it does not call <b>FsRtlDeleteKeyFromTunnelCache</b> and <b>FsRtlDeleteTunnelCache</b> at the same time from different threads. 

For more information about file name tunneling, see <a href="https://go.microsoft.com/fwlink/p/?linkid=3100&id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache">FsRtlDeleteTunnelCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache">FsRtlInitializeTunnelCache</a>
 

 

