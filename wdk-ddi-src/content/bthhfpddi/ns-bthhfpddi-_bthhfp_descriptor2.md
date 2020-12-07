---
UID: NS:bthhfpddi._BTHHFP_DESCRIPTOR2
title: _BTHHFP_DESCRIPTOR2 (bthhfpddi.h)
description: The BTHHFP_DESCRIPTOR2 data structure stores information describing a paired Handsfree profile (HFP) device.
old-location: audio\bthhfp_descriptor2.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["BTHHFP_DESCRIPTOR2 structure"]
ms.keywords: "*PBTHHFP_DESCRIPTOR2, BTHHFP_DESCRIPTOR2, BTHHFP_DESCRIPTOR2 structure [Audio Devices], PBTHHFP_DESCRIPTOR2, PBTHHFP_DESCRIPTOR2 structure pointer [Audio Devices], _BTHHFP_DESCRIPTOR2, audio.bthhfp_descriptor2, bthhfpddi/BTHHFP_DESCRIPTOR2, bthhfpddi/PBTHHFP_DESCRIPTOR2"
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
targetos: Windows
req.typenames: BTHHFP_DESCRIPTOR2, *PBTHHFP_DESCRIPTOR2
f1_keywords:
 - _BTHHFP_DESCRIPTOR2
 - bthhfpddi/_BTHHFP_DESCRIPTOR2
 - PBTHHFP_DESCRIPTOR2
 - bthhfpddi/PBTHHFP_DESCRIPTOR2
 - BTHHFP_DESCRIPTOR2
 - bthhfpddi/BTHHFP_DESCRIPTOR2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthhfpddi.h
api_name:
 - BTHHFP_DESCRIPTOR2
---

# _BTHHFP_DESCRIPTOR2 structure


## -description

The BTHHFP_DESCRIPTOR2  data structure stores information describing a paired Handsfree profile (HFP) device.

The HFP driver returns this data structure in the output buffer for the <a href="/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor2">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</a> request.

## -struct-fields

### -field InputPinCategory

KS pin category for the input function of the paired HFP device.

### -field OutputPinCategory

KS pin category for the output function of the paired HFP device.

### -field ContainerId

The PnP container ID for the paired HFP device.

### -field SupportsVolume

Indicates whether the paired HFP device supports remote volume control.

### -field VolumePropertyValuesSize

If remote volume control is supported, this member contains the size of the data returned by the <a href="/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a> request.

### -field FriendlyName

An indirect string identifying the human readable friendly name of the paired HFP device.

### -field SupportsNREC

Indicates whether the paired HFP device supports noise reduction / echo cancellation (NREC).

## -remarks

When the <i>SupportsNREC</i> parameter's value is TRUE, the audio driver should not support RAW mode pins. In this mode, the audio driver cannot support RAW mode pins because the remote Bluetooth device can enable its internal NREC processing at any time.


When <i>SupportsNREC</i> is set to FALSE, the audio driver should support RAW mode pins. The driver can, optionally, also support non-RAW modes and provide its own signal processing. In this case, the driver can provide signal processing  in one of three ways: within the driver code itself; by using its digital signal processing (DSP) module; by using its associated audio processing object (APO).

## -see-also

<a href="/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="/windows-hardware/drivers/audio/bluetooth-hfp-ddi-structures">Bluetooth HFP DDI Structures</a>



<a href="/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor2">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</a>



<a href="/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a>
