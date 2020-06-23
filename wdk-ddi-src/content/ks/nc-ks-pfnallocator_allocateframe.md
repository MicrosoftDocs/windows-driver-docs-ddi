---
UID: NC:ks.PFNALLOCATOR_ALLOCATEFRAME
title: PFNALLOCATOR_ALLOCATEFRAME (ks.h)
description: The KStrAllocateFrame routine describes a vendor-supplied frame allocation function.
old-location: stream\kstrallocateframe.htm
tech.root: stream
ms.assetid: 1b6eec23-82b4-4e8f-89d0-e76d6449906e
ms.date: 04/23/2018
keywords: ["PFNALLOCATOR_ALLOCATEFRAME callback function"]
ms.keywords: KStrAllocateFrame, KStrAllocateFrame routine [Streaming Media Devices], PFNALLOCATOR_ALLOCATEFRAME, ks/KStrAllocateFrame, ksfunc_a90af96e-53df-43f5-b847-ba1876b788fd.xml, stream.kstrallocateframe
f1_keywords:
 - "ks/KStrAllocateFrame"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- KStrAllocateFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNALLOCATOR_ALLOCATEFRAME callback function


## -description


The <i>KStrAllocateFrame</i> routine describes a vendor-supplied frame allocation function. 


## -parameters




### -param FileObject [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure for which to allocate frames.


### -param Frame [out]

A pointer to a caller-allocated buffer in which the new frame is returned.


## -returns



Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.




## -remarks



This type is used in the <b>AllocateFrame</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstreamallocator_functiontable">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-functiontable">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-functiontable">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstreamallocator_functiontable">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>
 

 

