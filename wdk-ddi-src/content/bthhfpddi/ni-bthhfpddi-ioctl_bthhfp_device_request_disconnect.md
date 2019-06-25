---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL removes the Handfree Profile (HFP) Service Level Connection that existed between the audio driver and the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_disconnect.htm
tech.root: audio
ms.assetid: BC28F8FC-5C0A-4999-89C1-FE25FD68B9FF
ms.date: 05/08/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT, IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT control, IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT control code [Audio Devices], audio.ioctl_bthhfp_device_request_disconnect, bthhfpddi/IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT</b> 
   IOCTL removes the Handfree Profile (HFP) Service Level Connection that existed between the audio driver and  the Bluetooth device.


## -ioctlparameters




### -input-buffer

N/A


### -input-buffer-length

N/A


### -output-buffer

N/A


### -output-buffer-length

N/A


### -in-out-buffer








### -inout-buffer-length








### -status-block

N/A


## -remarks



This request initiates the process to disconnect the Service Level Connection and ends without waiting for the disconnection to complete. Connection status can be determined using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.

The audio driver sends this request from its handler for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-oneshot-disconnect">KSPROPERTY_ONESHOT_DISCONNECT</a> KS property.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-oneshot-disconnect">KSPROPERTY_ONESHOT_DISCONNECT</a>
 

 

