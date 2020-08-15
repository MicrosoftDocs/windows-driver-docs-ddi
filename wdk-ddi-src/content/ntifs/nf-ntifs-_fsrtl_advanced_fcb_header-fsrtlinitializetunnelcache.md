---
UID: NF:ntifs.FsRtlInitializeTunnelCache
title: FsRtlInitializeTunnelCache function (ntifs.h)
description: The FsRtlInitializeTunnelCache routine initializes a new tunnel cache for a volume.
old-location: ifsk\fsrtlinitializetunnelcache.htm
tech.root: ifsk
ms.assetid: c499c11f-1de5-4c7f-aa26-62d2221c35bd
ms.date: 04/16/2018
keywords: ["FsRtlInitializeTunnelCache function"]
ms.keywords: FsRtlInitializeTunnelCache, FsRtlInitializeTunnelCache routine [Installable File System Drivers], fsrtlref_33e2bd32-4b53-4edc-8e61-7a0ffbab327a.xml, ifsk.fsrtlinitializetunnelcache, ntifs/FsRtlInitializeTunnelCache
f1_keywords:
 - "ntifs/FsRtlInitializeTunnelCache"
 - "FsRtlInitializeTunnelCache"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlInitializeTunnelCache
targetos: Windows
req.typenames: 
---

# FsRtlInitializeTunnelCache function


## -description


The <b>FsRtlInitializeTunnelCache</b> routine initializes a new tunnel cache for a volume.


## -parameters




### -param Cache 
[in]
Pointer to a per-volume TUNNEL structure for which the caller must provide resident storage in nonpaged pool. 


## -remarks



<b>FsRtlInitializeTunnelCache</b> initializes a new tunnel cache. File systems must call <b>FsRtlInitializeTunnelCache</b> before using any other <b>FsRtl...TunnelCache</b> routines on the tunnel cache.

File systems can use a per-volume tunnel cache to cache file names and other metadata for files that are being renamed or deleted. 

Entries are added to the tunnel cache by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdtotunnelcache">FsRtlAddToTunnelCache</a>. Each entry contains the file name and directory key for a file, and can also contain a fixed-size data packet of file-system-specific information. When the tunnel cache becomes full, older entries are removed automatically. 

For more information about file name tunneling, see <a href="https://go.microsoft.com/fwlink/p/?linkid=3100&id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdtotunnelcache">FsRtlAddToTunnelCache</a>
 

 

