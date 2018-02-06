---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_TARGET_MODE
title: "_D3DKMDT_VIDPN_TARGET_MODE"
author: windows-driver-content
description: The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode.
old-location: display\d3dkmdt_vidpn_target_mode.htm
old-project: display
ms.assetid: 9a20e955-7ef1-4cb7-8081-42fb69b55fb6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_a1ac1f39-cd89-458b-95b5-91fd5cbc507e.xml, d3dkmdt/D3DKMDT_VIDPN_TARGET_MODE, _D3DKMDT_VIDPN_TARGET_MODE, D3DKMDT_VIDPN_TARGET_MODE, D3DKMDT_VIDPN_TARGET_MODE structure [Display Devices], display.d3dkmdt_vidpn_target_mode
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_VIDPN_TARGET_MODE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_TARGET_MODE
---

# _D3DKMDT_VIDPN_TARGET_MODE structure


## -description


The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode.


## -syntax


````
typedef struct _D3DKMDT_VIDPN_TARGET_MODE {
  D3DKMDT_VIDEO_PRESENT_TARGET_MODE_ID Id;
  D3DKMDT_VIDEO_SIGNAL_INFO            VideoSignalInfo;
  D3DKMDT_MODE_PREFERENCE              Preference;
} D3DKMDT_VIDPN_TARGET_MODE;
````


## -struct-fields




### -field WireFormatAndPreference

 


### -field Id

An integer that identifies the target mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.


### -field VideoSignalInfo

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_signal_info.md">D3DKMDT_VIDEO_SIGNAL_INFO</a> structure that contains information about the target mode (for example, video standard, resolution, refresh rate).


### -field Preference

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_mode_preference.md">D3DKMDT_MODE_PREFERENCE</a> enumerator that indicates whether a particular mode is one of the modes that is preferred by the monitor that is connected to the video present target.


## -remarks


For more information about video present targets and VidPN target modes, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a> and <a href="https://msdn.microsoft.com/f1aa6277-7af6-4ba0-8ff1-d562f7029540">Enumerating Cofunctional VidPN Source and Target Modes</a>.



## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPN Target Mode Set Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_TARGET_MODE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

