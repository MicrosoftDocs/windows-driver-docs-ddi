---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_TARGET_MODE
title: "_D3DKMDT_VIDPN_TARGET_MODE"
author: windows-driver-content
description: The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode.
old-location: display\d3dkmdt_vidpn_target_mode.htm
old-project: display
ms.assetid: 9a20e955-7ef1-4cb7-8081-42fb69b55fb6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VIDPN_TARGET_MODE, D3DKMDT_VIDPN_TARGET_MODE structure [Display Devices], DmStructs_a1ac1f39-cd89-458b-95b5-91fd5cbc507e.xml, _D3DKMDT_VIDPN_TARGET_MODE, d3dkmdt/D3DKMDT_VIDPN_TARGET_MODE, display.d3dkmdt_vidpn_target_mode
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
-	D3DKMDT_VIDPN_TARGET_MODE
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_TARGET_MODE
---

# _D3DKMDT_VIDPN_TARGET_MODE structure


## -description


The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode.


## -struct-fields




### -field Id

An integer that identifies the target mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see <a href="https://msdn.microsoft.com/ebb37681-fa03-49f5-968b-87c9ff4ebae9">pfnCreateNewModeInfo</a>.


### -field VideoSignalInfo

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546625">D3DKMDT_VIDEO_SIGNAL_INFO</a> structure that contains information about the target mode (for example, video standard, resolution, refresh rate).


### -field Preference

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546061">D3DKMDT_MODE_PREFERENCE</a> enumerator that indicates whether a particular mode is one of the modes that is preferred by the monitor that is connected to the video present target.


## -remarks



For more information about video present targets and VidPN target modes, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a> and <a href="https://msdn.microsoft.com/f1aa6277-7af6-4ba0-8ff1-d562f7029540">Enumerating Cofunctional VidPN Source and Target Modes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPN Target Mode Set Interface</a>
 

 

