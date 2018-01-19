---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_COLOR_REGISTERS
title: IOCTL_VIDEO_SET_COLOR_REGISTERS
author: windows-driver-content
description: Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.
old-location: display\ioctl_video_set_color_registers.htm
old-project: display
ms.assetid: efaea94e-0cfd-49a7-b8dc-452aa006b024
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VIDEO_SET_COLOR_REGISTERS
req.alt-loc: Ntddvdeo.h
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
req.typenames: *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_COLOR_REGISTERS IOCTL



## -description

Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.



Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.



## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains a VIDEO_CLUT structure, specifying an array of RGB values to be set.


### -input-buffer-length

<text></text>

### -output-buffer
None


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## -remarks
