---
UID: NS:ntddvdeo._VIDEO_NUM_MODES
title: _VIDEO_NUM_MODES (ntddvdeo.h)
description: The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.
old-location: display\video_num_modes.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VIDEO_NUM_MODES structure"]
ms.keywords: "*PVIDEO_NUM_MODES, PVIDEO_NUM_MODES, PVIDEO_NUM_MODES structure pointer [Display Devices], VIDEO_NUM_MODES, VIDEO_NUM_MODES structure [Display Devices], Video_Structs_9e999162-309a-4902-8854-172c672bf1ea.xml, _VIDEO_NUM_MODES, display.video_num_modes, ntddvdeo/PVIDEO_NUM_MODES, ntddvdeo/VIDEO_NUM_MODES"
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
req.typenames: VIDEO_NUM_MODES, *PVIDEO_NUM_MODES
f1_keywords:
 - _VIDEO_NUM_MODES
 - ntddvdeo/_VIDEO_NUM_MODES
 - PVIDEO_NUM_MODES
 - ntddvdeo/PVIDEO_NUM_MODES
 - VIDEO_NUM_MODES
 - ntddvdeo/VIDEO_NUM_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - _VIDEO_NUM_MODES
 - PVIDEO_NUM_MODES
 - VIDEO_NUM_MODES
---

# _VIDEO_NUM_MODES structure


## -description

The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.

## -struct-fields

### -field NumModes

Specifies the number of modes supported by the device.

### -field ModeInformationLength

Is the length, in bytes, of the <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode_information">VIDEO_MODE_INFORMATION</a> structure that describes each of the modes supported by the device.

## -remarks

The miniport driver returns a VIDEO_NUM_MODES structure in response to an <a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_num_avail_modes">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_num_avail_modes">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode_information">VIDEO_MODE_INFORMATION</a>

