---
UID: NS:video._VP_SCATTER_GATHER_LIST
title: _VP_SCATTER_GATHER_LIST (video.h)
description: The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.
old-location: display\vp_scatter_gather_list.htm
tech.root: display
ms.assetid: 485a0e20-0fed-4055-985c-1ff6d5d1c3e9
ms.date: 05/10/2018
keywords: ["VP_SCATTER_GATHER_LIST structure"]
ms.keywords: "*PVP_SCATTER_GATHER_LIST, PVP_SCATTER_GATHER_LIST, PVP_SCATTER_GATHER_LIST structure pointer [Display Devices], VP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST structure [Display Devices], Video_Structs_0b59cadd-bf97-44c9-b987-d4dfc5eaaf15.xml, _VP_SCATTER_GATHER_LIST, display.vp_scatter_gather_list, video/PVP_SCATTER_GATHER_LIST, video/VP_SCATTER_GATHER_LIST"
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
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
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
f1_keywords:
 - _VP_SCATTER_GATHER_LIST
 - video/_VP_SCATTER_GATHER_LIST
 - PVP_SCATTER_GATHER_LIST
 - video/PVP_SCATTER_GATHER_LIST
 - VP_SCATTER_GATHER_LIST
 - video/VP_SCATTER_GATHER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - video.h
api_name:
 - VP_SCATTER_GATHER_LIST
---

# _VP_SCATTER_GATHER_LIST structure


## -description

The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.

## -struct-fields

### -field NumberOfElements

Specifies the number of scatter/gather elements in the <b>Elements</b> array member.

### -field Reserved

Reserved for system use.

### -field Elements

Specifies the number of scatter/gather elements in the <b>Elements</b> array member.

## -remarks

This structure is available in Windows XP and later.

The video port driver aggregates scatter/gather information in a VP_SCATTER_GATHER_LIST structure, passing it to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a> callback routine. The miniport driver uses this information when it sets up the video hardware for a DMA transfer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_vp_scatter_gather_element">VP_SCATTER_GATHER_ELEMENT</a>

