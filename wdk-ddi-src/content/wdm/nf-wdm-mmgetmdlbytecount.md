---
UID: NF:wdm.MmGetMdlByteCount
title: MmGetMdlByteCount macro
author: windows-driver-content
description: The MmGetMdlByteCount macro returns the length, in bytes, of the buffer described by the specified MDL.
old-location: kernel\mmgetmdlbytecount.htm
tech.root: Benchmark
ms.assetid: a0493418-2ce2-4917-bf9f-e4dc726a3847
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: MmGetMdlByteCount, MmGetMdlByteCount macro [Tools], k106_f750d750-c5ca-44cf-b8f1-f52d2eb8bc27.xml, kernel.mmgetmdlbytecount, wdm/MmGetMdlByteCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MmGetMdlByteCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmGetMdlByteCount macro


## -description


The <b>MmGetMdlByteCount</b> macro returns the length, in bytes, of the buffer described by the specified MDL.


## -parameters




### -param Mdl [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> structure that describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## -remarks



Callers of <b>MmGetMdlByteCount</b> can be running at any IRQL. Usually, callers are running at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554533">MmGetMdlByteOffset</a>
 

 

