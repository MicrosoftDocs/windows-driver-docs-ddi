---
UID: NS:sidebandaudio._SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
title: _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR (sidebandaudio.h)
description: Describes the characteristics of the audio Endpoint driver. 
ms.assetid: cd266b60-42df-4655-9d71-d35ddaa6c9a7
ms.date: 09/06/2018
f1_keywords:
 - "sidebandaudio/_SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR"
ms.keywords: _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, *PSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, 
req.header: sidebandaudio.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, *PSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR structure

## -description
Describes the characteristics of an Sideband audio Endpoint. Audio driver should query this information to build the KS filter representing this endpoint.

## -struct-fields

### -field CbSize
Size of Descriptor including storage for UNICODE_STRING and any additional data.

### -field ContainerId
Pnp Container ID for connected device. See <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-endpoint-container-id">Audio Endpoint Container ID</a>.

### -field Category
 KSPIN_DESCRIPTOR.Category to indicate form factor. Specifies a pointer to a KS pin category GUID. The KS pin category GUID identifies the general category of functionality that the pin provides. Examples of KS pin category GUIDs are KSNODETYPE_SPEAKER, KSNODETYPE_HEADPHONES, and KSNODETYPE_MICROPHONE, which are all defined in Ksmedia.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pin-category-property">Pin Category Property</a>.

### -field Direction
Specifies either KSPIN_DATAFLOW_IN or KSPIN_DATAFLOW_OUT. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-kspin_dataflow">KSPIN_DATAFLOW</a>.
 
### -field Capabilities
 Capabilities of the endpoint like (mute, volume, sidetone, etc.). See See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_endpoint_capabilities">SIDEBANDAUDIO_ENDPOINT_CAPABILITIES</a>.
 
### -field FriendlyName
Storage for friendly name is attached after descriptor and is included in cbSize. See <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/friendly-names-for-audio-endpoint-devices">Friendly Names for Audio Endpoint Devices</a>.
 
### -field VolumePropertyValuesSize
If remote volume control is supported, this member contains the size of the data returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_volumepropertyvalues">IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES</a> request.
 
### -field SidetoneVolumePropertyValueSize
If remote volume control is supported, this member contains the size of the data returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_sidetone_volumepropertyvalues">IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES</a> request.
 
## -remarks

## -see-also
[sidebandaudio.h](index.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_endpoint_capabilities">SIDEBANDAUDIO_ENDPOINT_CAPABILITIES</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_volumepropertyvalues">IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_sidetone_volumepropertyvalues">IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES</a>
