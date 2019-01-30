---
UID: NS:d3dkmdt._D3DKMDT_VIDEO_SIGNAL_INFO
title: "_D3DKMDT_VIDEO_SIGNAL_INFO" (d3dkmdt.h)
description: The D3DKMDT_VIDEO_SIGNAL_INFO structure contains information about a video signal driven by a video output on a display adapter.
old-location: display\d3dkmdt_video_signal_info.htm
tech.root: display
ms.assetid: 38d0a655-265b-46e0-8af3-de6757025588
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDEO_SIGNAL_INFO, D3DKMDT_VIDEO_SIGNAL_INFO structure [Display Devices], DmStructs_10882170-8ccd-481d-bb36-b0a1f706e395.xml, _D3DKMDT_VIDEO_SIGNAL_INFO, d3dkmdt/D3DKMDT_VIDEO_SIGNAL_INFO, display.d3dkmdt_video_signal_info
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDEO_SIGNAL_INFO
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_SIGNAL_INFO
---

# _D3DKMDT_VIDEO_SIGNAL_INFO structure


## -description


The D3DKMDT_VIDEO_SIGNAL_INFO structure contains information about a video signal driven by a video output on a display adapter.


## -struct-fields




### -field VideoStandard

A constant from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546632">D3DKMDT_VIDEO_SIGNAL_STANDARD</a> enumeration that indicates the video standard (if any) that defines the video signal.


### -field TotalSize

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff545977">D3DKMDT_2DREGION</a> structure that specifies the width and height (in pixels) of the entire video signal.


### -field ActiveSize

A D3DKMDT_2DREGION structure that specifies the width and height (in pixels) of the active portion of the video signal.


### -field VSyncFreq

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544641">D3DDDI_RATIONAL</a> structure that specifies the vertical refresh rate in Hz.


### -field HSyncFreq

A D3DDDI_RATIONAL structure that specifies the horizontal refresh rate in Hz.


### -field PixelRate

The pixel clock rate.


### -field AdditionalSignalInfo

Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.


### -field AdditionalSignalInfo.ScanLineOrdering

A constant from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544682">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a> enumeration that indicates the scanline ordering (for example, progressive or interlaced) of the video signal.

Supported starting with Windows 8.1.


### -field AdditionalSignalInfo.VSyncFreqDivider

The ratio of the VSync rate of a monitor that displays through a Miracast connected session to the VSync rate of the Miracast sink.

To avoid visual artifacts, the VSync rate of the display monitor that's connected to the Miracast sink must be an integer multiple of the VSync rate of the Miracast sink. The display miniport driver reports the latter rate to the operating system as the refresh rate of the desktop present path.

<div class="alert"><b>Note</b>  The operating system fails any attempt by the driver to add a target mode that results in a Miracast target having a VSync rate below 23.9 Hz.</div>
<div> </div>
For a non-Miracast target, the driver should set <b>VSyncFreqDivider</b> to zero.

Supported starting with Windows 8.1.


### -field AdditionalSignalInfo.Reserved

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.


### -field ScanLineOrdering

A constant from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544682">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a> enumeration that indicates the scanline ordering (for example, progressive or interlaced) of the video signal.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546617">D3DKMDT_VIDEO_PRESENT_TARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>
 

 

