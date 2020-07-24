---
UID: NF:wdm.MmGetMdlByteCount
title: MmGetMdlByteCount macro (wdm.h)
description: The MmGetMdlByteCount macro returns the length, in bytes, of the buffer described by the specified MDL.
old-location: kernel\mmgetmdlbytecount.htm
tech.root: Benchmark
ms.assetid: a0493418-2ce2-4917-bf9f-e4dc726a3847
ms.date: 02/15/2018
keywords: ["MmGetMdlByteCount macro"]
ms.keywords: MmGetMdlByteCount, MmGetMdlByteCount macro [Tools], k106_f750d750-c5ca-44cf-b8f1-f52d2eb8bc27.xml, kernel.mmgetmdlbytecount, wdm/MmGetMdlByteCount
f1_keywords:
 - "wdm/MmGetMdlByteCount"
 - "MmGetMdlByteCount"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- MmGetMdlByteCount
targetos: Windows
req.typenames: 
---

# MmGetMdlByteCount macro


## -description


The <b>MmGetMdlByteCount</b> macro returns the length, in bytes, of the buffer described by the specified MDL.


## -parameters




### -param Mdl [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> structure that describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.


## -remarks

**MmGetMdlByteCount** returns the length, in bytes, of the buffer described by Mdl. 


Callers of <b>MmGetMdlByteCount</b> can be running at any IRQL. Usually, callers are running at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlByteOffset</a>
 

 

