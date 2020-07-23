---
UID: NI:bthhfpddi.IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE
title: IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE (bthhfpddi.h)
description: The IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE IOCTL Gets the volume level setting of the Bluetooth device's speaker.
old-location: audio\ioctl_bthhfp_speaker_get_volume_status_update.htm
tech.root: audio
ms.assetid: CE122D3F-CD8F-47F5-88E0-AB0140A8DE1E
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE IOCTL"]
ms.keywords: IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE, IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE control, IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_speaker_get_volume_status_update, bthhfpddi/IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE"
 - "IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthhfpddi.h
api_name:
- IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE IOCTL


## -description


The <b>IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE</b> 
   IOCTL Gets the volume level setting of the Bluetooth device's speaker.


## -ioctlparameters




### -input-buffer

A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.


### -input-buffer-length

The size of a BOOL.


### -output-buffer

A LONG that represents the speaker's volume level in 1/65536 decibels.


### -output-buffer-length

The size of a LONG.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If a request is already pending the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.


## -remarks



This request will complete immediately if the input parameter is TRUE, or if the volume status has changed since the last request. Otherwise this request will remain pending until the volume status changes or the request is cancelled.

The audio driver sends this request to get the initial speaker and microphone volume levels, and sends subsequent requests "asking" to be  updated when the levels change. The driver stores the volume levels in appropriate context data. When the volume level changes, the audio driver generates the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-control-change">KSEVENT_CONTROL_CHANGE</a> event for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a> node in the KS topology of the speaker or microphone path.

The request’s output parameter is the same as the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-control-change">KSEVENT_CONTROL_CHANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a>
 

 

