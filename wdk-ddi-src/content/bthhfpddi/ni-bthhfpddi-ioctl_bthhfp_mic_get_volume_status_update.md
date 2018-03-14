---
UID: NI:bthhfpddi.IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE
title: IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE
author: windows-driver-content
description: The IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE IOCTL Gets the volume level setting of the Bluetooth device's microphone.
old-location: audio\ioctl_bthhfp_mic_get_volume_status_update.htm
old-project: audio
ms.assetid: 8BF4AEA4-B8EC-4C09-AEC8-5E47A0D715FB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE, IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_mic_get_volume_status_update, bthhfpddi/IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE IOCTL


## -description


The <b>IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE</b> IOCTL Gets the volume level setting of the Bluetooth device's microphone.


## -ioctlparameters




### -input-buffer

A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.


### -input-buffer-length

The size of a BOOL.


### -output-buffer

A LONG that represents the microphone's volume level in 1/65536 decibels.


### -output-buffer-length

The size of a LONG.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If a request is already pending the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.


## -remarks



This request will complete immediately if the input parameter is TRUE, or if the volume status has changed since the last request. Otherwise this request will remain pending until the volume status changes or the request is cancelled.

The audio driver sends this request to get the initial speaker and microphone volume levels, and sends subsequent requests "asking" to be  updated when the levels change. The driver stores the volume levels in appropriate context data. When the volume level changes, the audio driver generates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537128">KSEVENT_CONTROL_CHANGE</a> event for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> node in the KS topology of the speaker or microphone path.

The request’s output parameter is the same as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537128">KSEVENT_CONTROL_CHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>



 

 


