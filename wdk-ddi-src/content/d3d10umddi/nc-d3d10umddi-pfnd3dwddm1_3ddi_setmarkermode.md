---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_SETMARKERMODE
title: PFND3DWDDM1_3DDI_SETMARKERMODE (d3d10umddi.h)
description: Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\setmarkermode.htm
ms.assetid: 18B13509-7692-4336-937C-264B31A6FB78
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM1_3DDI_SETMARKERMODE, PFND3DWDDM1_3DDI_SETMARKERMODE callback, SetMarkerMode, SetMarkerMode callback function [Display Devices], d3d10umddi/SetMarkerMode, display.setmarkermode
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
 - "d3d10umddi/SetMarkerMode"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - SetMarkerMode
product:
 - Windows
---

# PFND3DWDDM1_3DDI_SETMARKERMODE callback function

## -description

Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Type

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_marker_type">D3DWDDM1_3DDI_MARKER_TYPE</a> enumeration that indicates the type of marker event  that the driver should support.

### -param Flags

A <b>UINT</b> value that indicates whether the driver should provide custom info in command buffers. If set to <b>D3DWDDM1_3DDI_SETMARKERMODE_CUSTOMDRIVEREVENTS</b>, the driver should annotate and instrument command buffers with custom event info. Otherwise, the driver should not annotate command buffers.

The annotation can be in the form of a text string in the English-US locale, or in the form of an index value to a location in a string table. For the latter option, the driver must also implement a function that describes the strings that the index values indicate.

## -returns

      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.

## -remarks

Follow these guidelines when you set up profile-type marker events in your user-mode driver, indicated by the <b>D3DWDDM1_3DDI_MARKER_TYPE_PROFILE</b> type:

<ol>
<li>Use lightweight instrumentation that doesn't produce a strong correlation with graphics command boundaries.</li>
<li>The driver must be able to sample the GPU time stamp at the end of the graphics pipeline.</li>
<li>Don't use sampling commands that place a high performance burden on the graphics pipeline, such as wait-for-idle commands. To be able to instrument profile-type marker events, your driver shouldn't have to flush the pipeline or caches.</li>
</ol>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_marker_type">D3DWDDM1_3DDI_MARKER_TYPE</a>

