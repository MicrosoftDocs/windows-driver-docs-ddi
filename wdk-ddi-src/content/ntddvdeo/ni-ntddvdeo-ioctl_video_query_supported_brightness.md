---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_SUPPORTED_BRIGHTNESS
title: IOCTL_VIDEO_QUERY_SUPPORTED_BRIGHTNESS
author: windows-driver-content
description: This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.
old-location: display\ioctl_video_query_supported_brightness.htm
old-project: display
ms.assetid: 00d549b1-9aa1-4d3d-8d23-209b0efaf639
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
req.alt-api: IOCTL_VIDEO_QUERY_SUPPORTED_BRIGHTNESS
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

# IOCTL_VIDEO_QUERY_SUPPORTED_BRIGHTNESS IOCTL



## -description

This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.



This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.



## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks
