---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDeleteTunnelCache
title: FsRtlDeleteTunnelCache function
author: windows-driver-content
description: The FsRtlDeleteTunnelCache routine deletes a tunnel cache.
old-location: ifsk\fsrtldeletetunnelcache.htm
old-project: ifsk
ms.assetid: bda13dc9-a9cc-4946-aadb-b073e5df787a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlDeleteTunnelCache routine [Installable File System Drivers], FsRtlDeleteTunnelCache, ifsk.fsrtldeletetunnelcache, fsrtlref_b5481e27-6ade-4057-8d63-3af814f9b80e.xml, ntifs/FsRtlDeleteTunnelCache
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlDeleteTunnelCache
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDeleteTunnelCache function


## -description


The <b>FsRtlDeleteTunnelCache</b> routine deletes a tunnel cache.


## -syntax


````
VOID FsRtlDeleteTunnelCache(
  _In_ TUNNEL *Cache
);
````


## -parameters




### -param Cache [in]

Pointer to the tunnel cache structure to delete. The tunnel cache must have been initialized by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>.


## -returns



None




## -remarks



<b>FsRtlDeleteTunnelCache</b> deletes all information contained in the tunnel cache. After the call to <b>FsRtlDeleteTunnelCache</b>, the tunnel cache is no longer valid.

Callers are responsible for synchronizing access to the <b>FsRtlDeleteTunnelCache</b> call. In other words, a file system must ensure that it does not call <b>FsRtlDeleteTunnelCache</b> at the same time it is calling another tunnel cache routine from a different thread. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlDeleteTunnelCache routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

