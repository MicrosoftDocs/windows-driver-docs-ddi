---
UID: NC:ks.PFNALLOCATOR_FREEFRAME
title: PFNALLOCATOR_FREEFRAME (ks.h)
description: The KStrFreeFrame routine describes a vendor-supplied frame deallocation function.
old-location: stream\kstrfreeframe.htm
tech.root: stream
ms.assetid: 6e998b5a-7f2a-4ab2-9382-f70476e5f34f
ms.date: 04/23/2018
ms.keywords: KStrFreeFrame, KStrFreeFrame routine [Streaming Media Devices], PFNALLOCATOR_FREEFRAME, ks/KStrFreeFrame, ksfunc_fbbb5f23-02d9-4670-8e9a-c157402d413e.xml, stream.kstrfreeframe
f1_keywords:
 - "ks/KStrFreeFrame"
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
- KStrFreeFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNALLOCATOR_FREEFRAME callback function

## -description

The *KStrFreeFrame* routine describes a vendor-supplied frame deallocation function. 

## -parameters

### -param FileObject [in]

Pointer to a [FILE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object) structure for which this frame has been allocated.

### -param Frame [in]

A pointer to a buffer containing the frame to release.

## -remarks

This type is used in the **FreeFrame** member of the [KSSTREAMALLOCATOR_FUNCTIONTABLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstreamallocator_functiontable) structure.

You can pass an instance of this structure as part of a [KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE](https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-functiontable) property request.

## -see-also

[KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE](https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-functiontable)

[KSSTREAMALLOCATOR_FUNCTIONTABLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstreamallocator_functiontable)
