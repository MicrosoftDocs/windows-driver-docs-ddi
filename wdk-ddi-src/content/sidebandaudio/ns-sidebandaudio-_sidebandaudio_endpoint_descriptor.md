---
UID: NS:sidebandaudio._SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
title: _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
author: windows-driver-content
description: Describes the characteristics of the audio Endpoint driver. 
ms.assetid: cd266b60-42df-4655-9d71-d35ddaa6c9a7
ms.date: 09/06/2018
ms.topic: struct
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
product: Windows
targetos: Windows
tech.root: audio
---

# _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR structure

## -description
Describes the characteristics of the audio Endpoint driver. This information does not change while the interface is enabled but can change while disabled.

## -struct-fields

### -field CbSize
Size of Descriptor including storage for UNICODE_STRING and any additional data.

### -field ContainerId
Pnp Container ID for connected device.

### -field Category
 KSPIN_DESCRIPTOR.Category to indicate form factor e.g. KSNODETYPE_HEADSET_MICROPHONE.

### -field Direction
 Indicates render/capture.
 
### -field Capabilities
 Capabilities of the endpoint like (mute, volume, sidetone, etc.).
 
### -field FriendlyName
Storage for friendly name is attached after descriptor and is included in cbSize.
 
### -field VolumePropertyValuesSize
Size of data returned by IOCTL_SBAUD_GET_VOLUMEPROPERTYVALUES.
 
### -field SidetoneVolumePropertyValueSize
Size of data returned by IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES.
 
## -remarks

## -see-also
[sidebandaudio.h](index.md)
