---
UID: NE:video.VIDEO_CHILD_TYPE
tech.root: display
title: VIDEO_CHILD_TYPE
ms.date: 11/01/2024
targetos: Windows
description: Learn more about VIDEO_CHILD_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: video.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - video.h
api_name:
 - VIDEO_CHILD_TYPE
 - PVIDEO_CHILD_TYPE
f1_keywords:
 - VIDEO_CHILD_TYPE
 - video/VIDEO_CHILD_TYPE
 - PVIDEO_CHILD_TYPE
 - video/PVIDEO_CHILD_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - VIDEO_CHILD_TYPE
---

## -description

The **VIDEO_CHILD_TYPE** enumeration specifies the type of child device that is attached to a video device.

## -enum-fields

### -field Monitor

Identifies a device that might have a DDC2 compliant EDID data structure. If the video miniport detects such a device, it should extract the EDID from the monitor and put that in the paged buffer provided by *videoprt.sys* in the callback to [**PVIDEO_HW_GET_CHILD_DESCRIPTOR**](nc-video-pvideo_hw_get_child_descriptor.md) and return this type in the **VideoChildType** parameter of that call. This EDID, if available, will be written to the registry. If the EDID is not available, nothing should be put in the buffer.

### -field NonPrimaryChip

Identifies another VGA chip on the video board that is not the primary VGA chip. This type is to be used if and only if the miniport detects more than one VGA chip on the board. Such an identifier will cause the *videoprt.sys* to create another DEVICE_EXTENSION and associated HW_DEVICE_EXTENSION to be associated with the chip so identified.

### -field VideoChip

Primary video chip on the video card.

### -field Other

Identifies some other video device attached to the video card. If the miniport detects such a device, it is to put a wide char string (WSTR) into the paged buffer provided by the videoprt.sys which is the PNP hardware identifier of the device. This string will be used to create a value of that name in the registry.
