---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
title: IOCTL_SBAUD_GET_MUTEPROPERTYVALUES (sidebandaudio.h)
description: 
ms.assetid: 83effb29-cc30-4be5-ac4c-e35b18b073f6
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
- IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_MUTEPROPERTYVALUES IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Audio driver can call this IOCTL to query the mute stepped data ranges and min/max values for all of the channels. These values should then be returned for KSPROPERTY_AUDIO_MUTE basic support.

## -ioctlparameters

### -input-buffer

Endpoint index.

### -input-buffer-length 

Size of ULONG.

### -output-buffer

KSPROPERTY_DESCRIPTION followed by KSPROPERTY_MEMBERSHEADER and Mute stepped data ranges as documented in [KSPROPERTY_DESCRIPTION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_description) and [KSPROPERTY_MEMBERSHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_membersheader).

### -output-buffer-length 

Size of KSPROPERTY_DESCRIPTION in addition to all the KSPROPERTY_MEMBERSHEADER and step ranges. This size was returned in SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR::MutePropertyValuesSize.

### -in-out-buffer

Input Endpoint Index and output KSPROPERTY_DESCRIPTION share the same buffer.

### -inout-buffer-length 

Allocated buffer should be of length SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR::MutePropertyValuesSize.

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
[KSPROPERTY_AUDIO_MUTE](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mute)

[KSNODEPROPERTY_AUDIO_CHANNEL](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksnodeproperty_audio_channel)
