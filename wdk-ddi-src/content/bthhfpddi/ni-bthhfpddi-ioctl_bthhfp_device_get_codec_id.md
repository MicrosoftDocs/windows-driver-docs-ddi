---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
title: IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
author: windows-driver-content
description: An audio driver can send an IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.
old-location: audio\ioctl_bthhfp_device_get_codec_id.htm
old-project: audio
ms.assetid: 38B67F0E-46A4-4AB5-B122-F5DE282FE52D
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CODEC_ID, IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code [Audio Devices], audio.ioctl_bthhfp_device_get_codec_id, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_CODEC_ID IOCTL


## -description


An audio driver can send an <b>IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</b> 
   control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.


## -ioctlparameters




### -input-buffer

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn798964">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value. Currently, only REQ_HFP_BYPASS_CODEC_ID_V1 is supported.


### -input-buffer-length

The size of an <a href="https://msdn.microsoft.com/library/windows/hardware/dn798964">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value.


### -output-buffer

A codec ID structure containing the codec ID information. Currently, only <a href="https://msdn.microsoft.com/library/windows/hardware/dn913703">HFP_BYPASS_CODEC_ID_V1</a> is supported.


### -output-buffer-length

The size of a codec ID structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the codec ID.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>
 

 

