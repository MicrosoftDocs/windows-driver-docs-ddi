---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS (d3d10umddi.h)
description: Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than VideoProcessorBlt. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorgetbehaviorhints.htm
ms.assetid: E6CBAFEE-9587-45D5-A6CD-4CA739AF279E
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS, PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback, d3d10umddi/pfnVideoProcessorGetBehaviorHints, display.videoprocessorgetbehaviorhints, pfnVideoProcessorGetBehaviorHints, pfnVideoProcessorGetBehaviorHints callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorGetBehaviorHints"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorGetBehaviorHints
product:
 - Windows
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback function

## -description

Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hVideoProcessor

Handle to the video processor object.

### -param OutputWidth

Indicates the width of the output surface.

### -param OutputHeight

Indicates the height of the output surface.

### -param OutputFormat

Indicates the output format of the video processor.

### -param StreamCount

The number of input streams to process.

### -param pStreams

An array of structures indicating the format and status of each stream.

### -param pBehaviorHints

Receives a combination of <b>D3DWDDM2_0DDI_VIDEO_PROCESSOR_MULTIPLANE_BEHAVIOR_HINTS</b> values indicting which of the operations would best be performed using multi-plane overlay hardware rather than with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

This function uses the current state, set via the <b>VideoProcessorSetOutput</b> and <b>VideoProcessorSetStream</b> set of  device driver interfaces (DDIs), and returns which operations could be performed more efficiently using multiple overlay hardware.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>

