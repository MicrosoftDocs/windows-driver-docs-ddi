---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_ORIENTATION_AWARENESS
title: "_D3DKMDT_MONITOR_ORIENTATION_AWARENESS"
author: windows-driver-content
description: The D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration is used to describe the ability of a video output device (on the display adapter) to detect changes in the orientation (rotation angle) of a connected external display device.
old-location: display\d3dkmdt_monitor_orientation_awareness.htm
old-project: display
ms.assetid: cea11e84-bff5-4189-9ed4-830049a44a4b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_MOA_INTERRUPTIBLE, D3DKMDT_MOA_NONE, D3DKMDT_MOA_POLLED, D3DKMDT_MOA_UNINITIALIZED, D3DKMDT_MONITOR_ORIENTATION_AWARENESS, D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration [Display Devices], DmEnums_d2570bc0-98c7-4402-b167-a4167715cc90.xml, _D3DKMDT_MONITOR_ORIENTATION_AWARENESS, d3dkmdt/D3DKMDT_MOA_INTERRUPTIBLE, d3dkmdt/D3DKMDT_MOA_NONE, d3dkmdt/D3DKMDT_MOA_POLLED, d3dkmdt/D3DKMDT_MOA_UNINITIALIZED, d3dkmdt/D3DKMDT_MONITOR_ORIENTATION_AWARENESS, display.d3dkmdt_monitor_orientation_awareness
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_MONITOR_ORIENTATION_AWARENESS
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_ORIENTATION_AWARENESS
---

# _D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration


## -description


The D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration is used to describe the ability of a video output device (on the display adapter) to detect changes in the orientation (rotation angle) of a connected external display device.


## -enum-fields




### -field D3DKMDT_MOA_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_ORIENTATION_AWARENESS has not yet been assigned a meaningful value.


### -field D3DKMDT_MOA_NONE

Indicates that the video output device is unable to determine the orientation of a connected external display device.


### -field D3DKMDT_MOA_POLLED

Indicates that the video output device can determine the orientation of a connected external display device, and the display miniport driver can be aware of changes in orientation by polling the video output device.


### -field D3DKMDT_MOA_INTERRUPTIBLE

Indicates that the video output device can generate an interrupt when the orientation of a connected external display device changes.


## -remarks



The <b>ChildCapabilities</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560995">DXGK_CHILD_CAPABILITIES</a> structure. The <b>Type.VideoOutput</b> member of a CHILD_CAPABILITIES structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562070">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure. The <b>MonitorOrientationAwareness</b> member of a VIDEO_OUTPUT_CAPABILITIES structure is a D3DKMDT_MONITOR_ORIENTATION_AWARENESS value.




## -see-also




<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
 

 

