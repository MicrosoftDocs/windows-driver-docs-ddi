---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
title: IOCTL_SBAUD_GET_MUTEPROPERTYVALUES (sidebandaudio.h)
description: "Learn more about: IOCTL_SBAUD_GET_MUTEPROPERTYVALUES IOCTL"
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_MUTEPROPERTYVALUES IOCTL"]
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
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
 - sidebandaudio/IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_MUTEPROPERTYVALUES
---

# IOCTL_SBAUD_GET_MUTEPROPERTYVALUES IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Audio driver can call this IOCTL to query the mute stepped data ranges and min/max values for all of the channels. These values should then be returned for [KSPROPERTY_AUDIO_MUTE](/windows-hardware/drivers/audio/ksproperty-audio-mute) basic support.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

A 0 based index value based on the number of Audio endpoints as reported by the [IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR](./ni-sidebandaudio-ioctl_sbaud_get_device_descriptor.md). This is a ULONG value from 0 to (N-1) where N is the number of Endpoints for the device.

### -input-buffer-length

Size of ULONG.

### -output-buffer

KSPROPERTY_DESCRIPTION followed by KSPROPERTY_MEMBERSHEADER and Mute stepped data ranges as documented in [KSPROPERTY_DESCRIPTION](../ks/ns-ks-ksproperty_description.md) and [KSPROPERTY_MEMBERSHEADER](../ks/ns-ks-ksproperty_membersheader.md).

If NULL, Irp->IoStatus.Information will be set to the number of bytes required for output buffer.

### -output-buffer-length

Size of KSPROPERTY_DESCRIPTION in addition to all the KSPROPERTY_MEMBERSHEADER and step ranges. This size is returned in SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR.MutePropertyValuesSize.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful, otherwise, Status to the appropriate error condition as a NTSTATUS code.

If output buffer is NULL, Irp->IoStatus.Status is set to STATUS_BUFFER_TOO_SMALL and Irp->IoStatus.Information is set to the number of bytes required for the output buffer.

If properly sized output buffer is provided, Irp->IoStatus.Information is set to the number of bytes written to the output buffer.

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Audio drivers that implement sideband audio should advertise endpoint Mute through a mute node in their KS Filter or through the Audio Engine Node. Both methods can utilize the basic support information provided by this IOCTL.

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[KSPROPERTY_AUDIO_MUTE](/windows-hardware/drivers/audio/ksproperty-audio-mute)

[KSNODEPROPERTY_AUDIO_CHANNEL](../ksmedia/ns-ksmedia-ksnodeproperty_audio_channel.md)

[IMiniportAudioEngineNode::GetDeviceChannelCount](../portcls/nf-portcls-iminiportaudioenginenode-getdevicechannelcount.md)

[sidebandaudio.h](index.md)