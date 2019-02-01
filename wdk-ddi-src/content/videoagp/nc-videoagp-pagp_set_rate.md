---
UID: NC:videoagp.PAGP_SET_RATE
title: PAGP_SET_RATE (videoagp.h)
description: The AgpSetRate function reprograms the data transfer rate of the AGP chipset.
old-location: display\agpsetrate.htm
tech.root: display
ms.assetid: 6885df05-8cc4-4ae0-b7ca-6fd94374cfbf
ms.date: 05/10/2018
ms.keywords: AgpSetRate, AgpSetRate callback function [Display Devices], PAGP_SET_RATE, PAGP_SET_RATE callback, VideoPort_Functions_4dfdb762-5156-4a06-9dd8-1766bbe3dbe4.xml, display.agpsetrate, videoagp/AgpSetRate
ms.topic: callback
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	UserDefined
api_location:
-	videoagp.h
api_name:
-	AgpSetRate
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_SET_RATE callback function


## -description

The <b>AgpSetRate</b> function reprograms the data transfer rate of the AGP chipset.

## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param AgpRate [in]

Specifies the transfer rate to be set. This value can be one of the following:

|Value|Meaning|
|--- |--- |
|VIDEO_AGP_RATE_1X|Single speed (66 Mhz)|
|VIDEO_AGP_RATE_2X|Two times single speed|
|VIDEO_AGP_RATE_4X|Four times single speed|
|VIDEO_AGP_RATE_8X|Eight times single speed|
 
## -returns

<b>AgpSetRate</b> returns <b>TRUE</b> if it was successful in changing the transfer rate; otherwise, it returns <b>FALSE</b>.

## -remarks

This function is available in Microsoft Windows XP and later.

The transfer rate set by the <b>AgpSetRate</b> function is persistent across changes in power state. The video miniport driver does not have to reset the AGP transfer rate when it changes from a low power state to a full power state. For information about change of power state, see <a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a>.

The <b>AgpSetRate</b> function can be used to change an AGP chipset's data transfer rate to any of the rates shown in the preceding table, as long as that transfer rate has not been explicitly eliminated in the INF file that loaded the display driver. For more information, see <a href="https://msdn.microsoft.com/2075a10f-a504-4bdc-8112-9c583c5084bb">Display INF File Sections</a>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570528">VIDEO_PORT_AGP_INTERFACE_2</a>
