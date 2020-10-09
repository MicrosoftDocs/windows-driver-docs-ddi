---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
title: IOCTL_BTHHFP_DEVICE_GET_CODEC_ID (bthhfpddi.h)
description: An audio driver can send an IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.
old-location: audio\ioctl_bthhfp_device_get_codec_id.htm
tech.root: audio
ms.assetid: 38B67F0E-46A4-4AB5-B122-F5DE282FE52D
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_GET_CODEC_ID IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CODEC_ID, IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control, IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code [Audio Devices], audio.ioctl_bthhfp_device_get_codec_id, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: 
f1_keywords:
 - IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
 - bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthhfpddi.h
api_name:
 - IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
---

# IOCTL_BTHHFP_DEVICE_GET_CODEC_ID IOCTL


## -description

An audio driver can send an <b>IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</b> 
   control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.

## -ioctlparameters

### -input-buffer

An <a href="/windows-hardware/drivers/ddi/bthhfpddi/ne-bthhfpddi-_hfp_bypass_codec_id_version">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value. Currently, only REQ_HFP_BYPASS_CODEC_ID_V1 is supported.

### -input-buffer-length

The size of an <a href="/windows-hardware/drivers/ddi/bthhfpddi/ne-bthhfpddi-_hfp_bypass_codec_id_version">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value.

### -output-buffer

A codec ID structure containing the codec ID information. Currently, only <a href="/windows-hardware/drivers/ddi/bthhfpddi/ns-bthhfpddi-_hfp_bypass_codec_id_v1">HFP_BYPASS_CODEC_ID_V1</a> is supported.

### -output-buffer-length

The size of a codec ID structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the codec ID.

## -see-also

<a href="/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>