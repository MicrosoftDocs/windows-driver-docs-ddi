---
UID: NS:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I
title: "_DISPLAYID_DETAILED_TIMING_TYPE_I"
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I structure specifies an additional target mode set for a video present target.
old-location: display\displayid_detailed_timing_type_i.htm
old-project: display
ms.assetid: 7b3fa3a4-a77a-4c5f-b157-1fbdc3a7be33
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DISPLAYID_DETAILED_TIMING_TYPE_I, DISPLAYID_DETAILED_TIMING_TYPE_I structure [Display Devices], DmStructs_75d5fd93-c7ae-4a57-9843-427c53a9416f.xml, _DISPLAYID_DETAILED_TIMING_TYPE_I, d3dkmdt/DISPLAYID_DETAILED_TIMING_TYPE_I, display.displayid_detailed_timing_type_i
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	DISPLAYID_DETAILED_TIMING_TYPE_I
product: Windows
targetos: Windows
req.typenames: DISPLAYID_DETAILED_TIMING_TYPE_I
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I structure


## -description


The DISPLAYID_DETAILED_TIMING_TYPE_I structure specifies an additional target mode set for a video present target.


## -struct-fields




### -field HorizontalActivePixels

[in] The number of active pixels in the horizontal direction.


### -field HorizontalBlankPixels

[in] The number of blank pixels in the horizontal direction.


### -field HorizontalSyncWidth

[in] The horizontal sync interval, in pixels.


### -field VerticalActiveLines

[in] The number of active scan lines.


### -field VerticalBlankLines

[in] The number of blank scan lines.


### -field VerticalSyncWidth

[in] The vertical sync interval, in number of lines.


#### - AspectRatio

[in] The display aspect ratio, which must be one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554017">DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO</a> enumeration.


#### - HorizontalFrontPorch

[in] The horizontal front porch interval, in pixels. The front porch is the blanking interval before the sync pulse.


#### - HorizontalSyncPolarity

[in] The horizontal sync polarity, which must be one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554026">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a> enumeration.


#### - PixelClock

[in] The display pixel clock rate, in units of 10 KHz. Clock rate must be between 1 MHz and 10 GHz, inclusive.


#### - PreferredTiming


       [in] Indicates whether the first 128-byte block of a monitor's Extended Display Identification Data <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">Extended Display Identification Data (EDID)</a> contains detailed timing data. This must be 1 if the display conforms to EDID version 1.3 and later.
      


#### - Reserved

[in] Reserved for system use.


#### - ScanningType

[in] The frame scanning type. Must be one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554019">DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE</a> enumeration.


#### - StereoMode

[in] The display stereo vision mode. Must be one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554023">DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE</a> enumeration.


#### - VerticalFrontPorch

[in] The vertical front porch interval, in number of lines. The front porch is the blanking interval before the sync pulse.


#### - VerticalSyncPolarity

[in] The vertical sync polarity. Must be one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554026">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a> enumeration.


## -remarks



The Microsoft DirectX graphics kernel subsystem fills this structure by reading the additional target mode data that is stored in the registry at the following path:

<b>HKEY_LOCAL_MACHINE\ SYSTEM\ CurrentControlSet\ Control\ GraphicsDrivers\ AdditionalTargetModeLists</b>

The graphics kernel subsystem also validates that each registry value meets the requirements described above for each respective member.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554017">DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554019">DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554023">DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554026">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DISPLAYID_DETAILED_TIMING_TYPE_I structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

