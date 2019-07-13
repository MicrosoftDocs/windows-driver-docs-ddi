---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES
title: IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES (sidebandaudio.h)
description: 
ms.assetid: 11e26b8c-2c82-46b5-907f-7e2b81f0e16a
ms.date: 10/05/2018
ms.topic: ioctl
req.header: sidebandaudio.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.max-support:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Audio driver can call this IOCTL to query the volume stepped data ranges and min/max values for all of the channels. These values should then be returned for KSPROPERTY_AUDIO_VOLUMELEVEL basic support.



## -ioctlparameters

### -input-buffer

Endpoint index.

### -input-buffer-length

Size of ULONG.

### -output-buffer

KSPROPERTY_DESCRIPTION followed by KSPROPERTY_MEMBERSHEADER and Volume stepped data ranges as documented in <a href='https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_description'>KSPROPERTY_DESCRIPTION</a> and <a href='https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_membersheader'>KSPROPERTY_MEMBERSHEADER</a>.

### -output-buffer-length 

Size of KSPROPERTY_DESCRIPTION in addition to all the KSPROPERTY_MEMBERSHEADER and step ranges. This size was returned in SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR::VolumePropertyValuesSize.

### -in-out-buffer

Input Endpoint Index and output KSPROPERTY_DESCRIPTION share the same buffer.

### -inout-buffer-length 

Allocated buffer should be of length SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR::VolumePropertyValuesSize.

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksnodeproperty_audio_channel">KSNODEPROPERTY_AUDIO_CHANNEL</a>
