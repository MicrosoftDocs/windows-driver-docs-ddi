---
UID: NF:ntifs.FsRtlDeleteTunnelCache
title: FsRtlDeleteTunnelCache function (ntifs.h)
description: The FsRtlDeleteTunnelCache routine deletes a tunnel cache.
old-location: ifsk\fsrtldeletetunnelcache.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlDeleteTunnelCache function"]
ms.keywords: FsRtlDeleteTunnelCache, FsRtlDeleteTunnelCache routine [Installable File System Drivers], fsrtlref_b5481e27-6ade-4057-8d63-3af814f9b80e.xml, ifsk.fsrtldeletetunnelcache, ntifs/FsRtlDeleteTunnelCache
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlDeleteTunnelCache
 - ntifs/FsRtlDeleteTunnelCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlDeleteTunnelCache
---

# FsRtlDeleteTunnelCache function


## -description

The <b>FsRtlDeleteTunnelCache</b> routine deletes a tunnel cache.

## -parameters

### -param Cache [in]


Pointer to the tunnel cache structure to delete. The tunnel cache must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache">FsRtlInitializeTunnelCache</a>.

## -remarks

<b>FsRtlDeleteTunnelCache</b> deletes all information contained in the tunnel cache. After the call to <b>FsRtlDeleteTunnelCache</b>, the tunnel cache is no longer valid.

Callers are responsible for synchronizing access to the <b>FsRtlDeleteTunnelCache</b> call. In other words, a file system must ensure that it does not call <b>FsRtlDeleteTunnelCache</b> at the same time it is calling another tunnel cache routine from a different thread. 

For more information about file name tunneling, see <a href="https://go.microsoft.com/fwlink/p/?linkid=3100&id=172190">Microsoft Knowledge Base Article 172190</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache">FsRtlInitializeTunnelCache</a>
