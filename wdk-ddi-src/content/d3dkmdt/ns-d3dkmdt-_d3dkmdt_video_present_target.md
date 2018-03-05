---
UID: NS:d3dkmdt._D3DKMDT_VIDEO_PRESENT_TARGET
title: "_D3DKMDT_VIDEO_PRESENT_TARGET"
author: windows-driver-content
description: The D3DKMDT_VIDEO_PRESENT_TARGET structure contains information about a video present target.
old-location: display\d3dkmdt_video_present_target.htm
old-project: display
ms.assetid: e36aba12-51fc-486c-a92c-47f72a4bcb0a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_VIDEO_PRESENT_TARGET, D3DKMDT_VIDEO_PRESENT_TARGET structure [Display Devices], DmStructs_ef451c58-7ee5-4c52-9afe-9aab45114186.xml, _D3DKMDT_VIDEO_PRESENT_TARGET, d3dkmdt/D3DKMDT_VIDEO_PRESENT_TARGET, display.d3dkmdt_video_present_target
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DKMDT_VIDEO_PRESENT_TARGET
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_PRESENT_TARGET
---

# _D3DKMDT_VIDEO_PRESENT_TARGET structure


## -description


The D3DKMDT_VIDEO_PRESENT_TARGET structure contains information about a video present target.


## -syntax


````
typedef struct _D3DKMDT_VIDEO_PRESENT_TARGET {
  D3DDDI_VIDEO_PRESENT_TARGET_ID        Id;
  D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY       VideoOutputTechnology;
  DXGK_CHILD_DEVICE_HPD_AWARENESS       VideoOutputHpdAwareness;
  D3DKMDT_MONITOR_ORIENTATION_AWARENESS MonitorOrientationAwareness;
  BOOLEAN                               SupportsSdtvModes;
} D3DKMDT_VIDEO_PRESENT_TARGET;
````


## -struct-fields




### -field Id

An integer that uniquely identifies the video present target.


### -field VideoOutputTechnology

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_video_output_technology.md">D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY</a> enumerator that indicates the target's output technology (for example HD15, DVI, HDMI).


### -field VideoOutputHpdAwareness

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_child_device_hpd_awareness.md">DXGK_CHILD_DEVICE_HPD_AWARENESS</a> enumeration that indicates the target's ability to detect that a monitor has been hot plugged or unplugged.


### -field MonitorOrientationAwareness

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_monitor_orientation_awareness.md">D3DKMDT_MONITOR_ORIENTATION_AWARENESS</a> enumerator that indicates the target's ability to detect that a connected monitor (or other display device) has been rotated.


### -field SupportsSdtvModes

Indicates whether the video output supports standard definition TV (SDTV) modes.


## -remarks



The D3DDDI_VIDEO_PRESENT_TARGET_ID data type is defined in <i>D3dukmdt.h</i>.

Video present target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

For more information about video present targets, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a>.




## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_present_source.md">D3DKMDT_VIDEO_PRESENT_SOURCE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_PRESENT_TARGET structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

