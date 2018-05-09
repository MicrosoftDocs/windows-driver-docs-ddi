---
UID: NI:bthhfpddi.IOCTL_BTHHFP_SPEAKER_SET_VOLUME
title: IOCTL_BTHHFP_SPEAKER_SET_VOLUME
author: windows-driver-content
description: The IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL sets the volume level for the speaker of the Bluetooth device.
old-location: audio\ioctl_bthhfp_speaker_set_volume.htm
old-project: audio
ms.assetid: D08D9CEB-8A5C-41E6-AF05-2AE8719DD462
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_BTHHFP_SPEAKER_SET_VOLUME, IOCTL_BTHHFP_SPEAKER_SET_VOLUME control, IOCTL_BTHHFP_SPEAKER_SET_VOLUME control code [Audio Devices], audio.ioctl_bthhfp_speaker_set_volume, bthhfpddi/IOCTL_BTHHFP_SPEAKER_SET_VOLUME
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
-	IOCTL_BTHHFP_SPEAKER_SET_VOLUME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL


## -description


The <b>IOCTL_BTHHFP_SPEAKER_SET_VOLUME</b> IOCTL sets the volume level for the  
   speaker of the Bluetooth device. 


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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

N/A


## -remarks



The audio driver sends this request when handling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> node in the KS topology of the speaker path. The request’s input parameter is the same as the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a>
 

 

