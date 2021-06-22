---
UID: NS:ksmedia.tagKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
tech.root: stream
title: KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
ms.date: 06/24/2021
targetos: Windows
description: The KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK structure contains information about the dimensions of the background mask as well as its coverage of the frame it is inferred from, which is the frame that is outputted by the stream.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK, *PKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - PKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
f1_keywords:
 - tagKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - ksmedia/tagKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - PKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - ksmedia/PKSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
 - ksmedia/KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK
dev_langs:
 - c++
---

## -description

The **KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK** structure contains information about the dimensions of the background mask as well as its coverage of the frame it is inferred from, which is the frame that is outputted by the stream.

## -struct-fields

### -field Header

A [**KSCAMERA_METADATA_ITEMHEADER**](ns-ksmedia-tagkscamera_metadata_itemheader.md) structure that contains the metadata header information that is filled by the camera driver.

### -field MaskCoverageBoundingBox

Bounding box of processed mask area, in original image coordinates.

If the driver can supply a mask that covers the whole field of view, then this bounding box should be of the same dimension as the frame it corresponds to.

### -field MaskResolution

Width and height of mask data contained in the contiguous *MaskData* buffer in this struct.

This should correspond to the *MaskResolution* member of the related [**KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS**](ns-ksmedia-kscamera_extendedprop_backgroundsegmentation_configcaps.md) returned by a GET of the [**KSPROPERTY_CAMERACONTROL_EXTENDED_BACKGROUNDSEGMENTATION**](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-backgroundsegmentation)property.

### -field ForegroundBoundingBox

Bounding box of all foreground pixels in the mask, in mask coordinates.

This may help speed up processing by the app by considering only a portion of the mask. This can be left to cover the whole mask if not calculated by the driver. However when it does not cover the whole mask, then the mask data outside of this bounding box shall be considered background (zero) values regardless of their actual values.

### -field MaskData

MaskResolution.cx * MaskResolution.cy BYTE values are populated as a contiguous buffer.  

The value represents the normalized confidence score of a pixel being part of the background or the foreground, where a value of "0" designates 100% certainty of a background pixel and "255" designates 100% certainty of a foreground pixel.

The size of the buffer trails beyond the MaskData field and the size is determined by the size of the MetadataSize field.  MetadataSize should be equal to FIELD_OFFSET(KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK, MaskData) + [MaskResolution.cx * MaskResolution.cy].

## -remarks

## -see-also

[KSPROPERTY_CAMERACONTROL_EXTENDED_BACKGROUNDSEGMENTATION](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-backgroundsegmentation)

[KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS](ns-ksmedia-kscamera_extendedprop_backgroundsegmentation_configcaps.md)
