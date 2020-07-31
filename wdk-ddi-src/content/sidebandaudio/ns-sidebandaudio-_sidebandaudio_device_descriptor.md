---
UID: NS:sidebandaudio._SIDEBANDAUDIO_DEVICE_DESCRIPTOR
title: _SIDEBANDAUDIO_DEVICE_DESCRIPTOR (sidebandaudio.h)
description: Describes the number of endpoints on the device.
ms.assetid: 6eb69211-4a34-4e63-ae42-80fd298957d8
ms.date: 09/06/2018
keywords: ["_SIDEBANDAUDIO_DEVICE_DESCRIPTOR structure"]
f1_keywords:
 - "sidebandaudio/_SIDEBANDAUDIO_DEVICE_DESCRIPTOR"
 - "_SIDEBANDAUDIO_DEVICE_DESCRIPTOR"
ms.keywords: _SIDEBANDAUDIO_DEVICE_DESCRIPTOR, SIDEBANDAUDIO_DEVICE_DESCRIPTOR, *PSIDEBANDAUDIO_DEVICE_DESCRIPTOR, 
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
req.typenames: SIDEBANDAUDIO_DEVICE_DESCRIPTOR, *PSIDEBANDAUDIO_DEVICE_DESCRIPTOR
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- _SIDEBANDAUDIO_DEVICE_DESCRIPTOR
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_DEVICE_DESCRIPTOR structure

## -description
Describes the number of endpoints on the device.

## -struct-fields

### -field NumberOfEndpoints
Number of Audio endpoints on the devices that can be sidebanded.  This number excludes the feedback endpoints.

## -remarks
A device can contain multiple audio endpoints that can be used in Sideband mode. The number of endpoints can be used to iterate through all the endpoints contained in the device using a 0 based index (0 to n-1).
Driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_endpoint_descriptor">IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR</a> iteratively to get details about each of the endpoints.

## -see-also
[sidebandaudio.h](index.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_endpoint_descriptor">IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR</a>
