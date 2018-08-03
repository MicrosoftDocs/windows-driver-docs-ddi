---
UID: NE:portabledevice.tagWPD_VIDEO_SCAN_TYPES
title: tagWPD_VIDEO_SCAN_TYPES
author: windows-driver-content
description: The WPD_VIDEO_SCAN_TYPES enumeration type describes how the fields in a video file are encoded.
old-location: wpddk\wpd_video_scan_types.htm
tech.root: wpd_dk
ms.assetid: e2b46187-83b0-43fa-ab5f-80ca375bdcf7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: WPD_VIDEO_SCAN_TYPES, WPD_VIDEO_SCAN_TYPES enumeration, WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_LOWER_FIRST, WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_UPPER_FIRST, WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_LOWER_FIRST, WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_UPPER_FIRST, WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE, WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE_AND_PROGRESSIVE, WPD_VIDEO_SCAN_TYPE_PROGRESSIVE, WPD_VIDEO_SCAN_TYPE_UNUSED, enumeration, portabledevice/WPD_VIDEO_SCAN_TYPES, portabledevice/WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_LOWER_FIRST, portabledevice/WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_UPPER_FIRST, portabledevice/WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_LOWER_FIRST, portabledevice/WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_UPPER_FIRST, portabledevice/WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE, portabledevice/WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE_AND_PROGRESSIVE, portabledevice/WPD_VIDEO_SCAN_TYPE_PROGRESSIVE, portabledevice/WPD_VIDEO_SCAN_TYPE_UNUSED, tagWPD_VIDEO_SCAN_TYPES, wpddk.wpd_video_scan_types
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portabledevice.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PortableDevice.h
api_name:
-	WPD_VIDEO_SCAN_TYPES
product: Windows
targetos: Windows
req.typenames: WPD_VIDEO_SCAN_TYPES
---

# tagWPD_VIDEO_SCAN_TYPES enumeration


## -description



The <b>WPD_VIDEO_SCAN_TYPES</b> enumeration type describes how the fields in a video file are encoded.




## -enum-fields




### -field WPD_VIDEO_SCAN_TYPE_UNUSED

The scan type has not been defined for this video file, or is not applicable.


### -field WPD_VIDEO_SCAN_TYPE_PROGRESSIVE

A progressive scan video file.


### -field WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_UPPER_FIRST

An interleaved video file where the fields alternate and the upper field (with line 1) is drawn first. For more information, see the Remarks section.


### -field WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED_LOWER_FIRST

An interleaved video file where the fields alternate and the lower field (with line 2) is drawn first. For more information, see <b>Remarks</b>, following this section.


### -field WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_UPPER_FIRST

An interleaved video file where the fields are sent as contiguous samples and the upper field (with line 1) is drawn first. For more information, see <b>Remarks</b>, following this section.


### -field WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE_LOWER_FIRST

An interleaved video file where the fields are sent as contiguous samples and the lower field (with line 2) is sent first.


### -field WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE

A video file with a mix of interlacing modes.


### -field WPD_VIDEO_SCAN_TYPE_MIXED_INTERLACE_AND_PROGRESSIVE

A video file with a mix of interlaced and progressive modes.


## -remarks



This enumeration is used by the <a href="https://msdn.microsoft.com/e5e58196-7470-4e17-8f4c-bb6be8f117b9">WPD_VIDEO_SCAN_TYPE</a> property.

There are two types of interleaved file formats that are specified by this enumeration. WPD_VIDEO_SCAN_TYPE_FIELD_INTERLEAVED refers to a file format where frames are delivered as they were scanned—fields alternate and data goes line by line, as shown here:

<b>Frame 1</b>

Field 1: Line 1

Field 2: Line 1

Field 1: Line 2

Field 2: Line 2

Field 1: Line 3

Field 2: Line 3

...

WPD_VIDEO_SCAN_TYPE_FIELD_SINGLE refers to a file format where each field is stored in a single block of scan lines, and fields are stored sequentially, as shown here:

<b>Frame 1</b>

Field 1: Line 1

Field 1: Line 2

Field 1: Line 3

...

Followed by

Field 2: Line 1

Field 2: Line 2

Field 2: Line 3

...




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597672">Structures and Enumeration Types</a>
 

 

