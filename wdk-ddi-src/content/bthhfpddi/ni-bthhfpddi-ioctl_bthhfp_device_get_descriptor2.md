---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
title: IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL Gets descriptive information about the paired Handsfree profile (HFP) device.
old-location: audio\ioctl_bthhfp_device_get_descriptor2.htm
tech.root: audio
ms.assetid: B72D0236-1C2B-4D0B-86B4-4E9B667BA1B3
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2, IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 control, IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 control code [Audio Devices], audio.ioctl_bthhfp_device_get_descriptor2, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2"
 - "IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2"
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
- IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</b> 
   IOCTL Gets descriptive information about the paired Handsfree profile (HFP) device.

This IOCTL is available in Windows 8.1 and later operating systems, and it supersedes <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer

A buffer containing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ns-bthhfpddi-_bthhfp_descriptor2">BTHHFP_DESCRIPTOR2</a> structure followed by any other data that is referenced by the structure. This is true,  if the output buffer size is sufficient and the request succeeds. In particular, the buffer includes storage for the string that is referenced by the <i>FriendlyName</i> field of the <b>BTHHFP_DESCRIPTOR2</b> structure.


### -output-buffer-length

The size of a <b>BTHHFP_DESCRIPTOR2</b> structure and referenced data.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer. Note this can be larger than the size of the <b>BTHHFP_DESCRIPTOR2</b> structure, as the output buffer may contain other data referenced by the <b>BTHHFP_DESCRIPTOR2</b> structure.

If Status is set to STATUS_BUFFER_TOO_SMALL, then <i>Information</i> is the size of the buffer that the caller should allocate for this request.


## -remarks



The audio driver sends this request to obtain information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface. The information does not change while the interface is enabled, but can change while the interface is disabled. Therefore the audio driver sends this request shortly after discovering an enabled device interface and uses the information to build an appropriate KSFILTER_DESCRIPTOR structure.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and the <i>Information</i> parameter will  contain the required buffer size. The audio driver then allocates the necessary storage and sends the request again. Typically an audio driver will keep a pointer to this storage location in its device context for reference during later activity.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ns-bthhfpddi-_bthhfp_descriptor2">BTHHFP_DESCRIPTOR2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>
 

 

