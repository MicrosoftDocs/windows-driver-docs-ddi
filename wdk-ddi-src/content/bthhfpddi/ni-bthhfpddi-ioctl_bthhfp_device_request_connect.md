---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_connect.htm
tech.root: audio
ms.assetid: CE591873-FFDC-49A2-BB75-FE445338D633
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT, IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT control, IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT control code [Audio Devices], audio.ioctl_bthhfp_device_request_connect, bthhfpddi/IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT"
 - "IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT"
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
- IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT</b> 
   IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.


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



This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.

The audio driver sends this request from its handler for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-oneshot-reconnect">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-oneshot-reconnect">KSPROPERTY_ONESHOT_RECONNECT</a>
 

 

