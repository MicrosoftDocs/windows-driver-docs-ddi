---
UID: NI:bthhfpddi.IOCTL_BTHHFP_MIC_SET_VOLUME
title: IOCTL_BTHHFP_MIC_SET_VOLUME (bthhfpddi.h)
description: The IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL sets the volume level of the microphone for the Bluetooth device.
old-location: audio\ioctl_bthhfp_mic_set_volume.htm
tech.root: audio
ms.assetid: 438BB68B-9E09-4033-B38E-C1C28D00D43C
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL"]
ms.keywords: IOCTL_BTHHFP_MIC_SET_VOLUME, IOCTL_BTHHFP_MIC_SET_VOLUME control, IOCTL_BTHHFP_MIC_SET_VOLUME control code [Audio Devices], audio.ioctl_bthhfp_mic_set_volume, bthhfpddi/IOCTL_BTHHFP_MIC_SET_VOLUME
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_MIC_SET_VOLUME"
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
- IOCTL_BTHHFP_MIC_SET_VOLUME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL


## -description


The <b>IOCTL_BTHHFP_MIC_SET_VOLUME</b> 
   IOCTL sets the  volume level of the microphone for the Bluetooth device.


## -ioctlparameters




### -input-buffer

A LONG that represents the volume level in 1/65536 decibels.


### -input-buffer-length

The size of a LONG.


### -output-buffer

N/A


### -output-buffer-length

N/A


### -in-out-buffer








### -inout-buffer-length








### -status-block

N/A


## -remarks



The audio driver sends this request when handling the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a> node in the KS topology of the microphone path. The request’s input parameter is the same as the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a>
 

 

