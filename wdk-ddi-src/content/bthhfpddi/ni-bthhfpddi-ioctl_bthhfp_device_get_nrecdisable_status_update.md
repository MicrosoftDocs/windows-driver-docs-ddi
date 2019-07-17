---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
title: IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL Gets noise reduction / echo cancellation (NREC) Disable status updates from the remote Bluetooth device.
old-location: audio\ioctl_bthhfp_device_get_nrecdisable_status_update.htm
tech.root: audio
ms.assetid: 2AA3098D-B3CA-4515-AC53-C78E2060D798
ms.date: 05/08/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE, IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE control, IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_device_get_nrecdisable_status_update, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
ms.topic: ioctl
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthhfpddi.h
api_name:
- IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE</b> 
   IOCTL Gets noise reduction / echo cancellation (NREC) Disable status updates from the remote Bluetooth device.

This IOCTL is available in Windows 8.1 and later operating systems.


## -ioctlparameters




### -input-buffer

A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.


### -input-buffer-length

The size of a BOOL.


### -output-buffer

A BOOL that indicates the new NREC Disable status. See <b>Remarks</b> for additional information.


### -output-buffer-length

The size of a BOOL.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If a request is already pending, then the new request fails with an error code of STATUS_INVALID_DEVICE_REQUEST.


## -remarks



When the NREC Disable status is TRUE, it shows that the remote Bluetooth device has disabled  any system-based NREC processing, implying that the remote device has enabled its own NREC signal processing. In this scenario, the audio driver should disable any of its own NREC processing, regardless of whether the processing is being done within the driver code itself, in its digital signal processing (DSP) module, or its audio processing object (APO). 

Additionally, in this scenario where NREC is enabled in the remote Bluetooth device, the driver’s APO should return "NREC" in its list of effects, to let applications know that NREC processing is enabled.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>
 

 

