---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
title: IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL Gets a connection status update.
old-location: audio\ioctl_bthhfp_device_get_connection_status_update.htm
tech.root: audio
ms.assetid: 19863998-99AB-427E-BFBD-B8EF42C74DEF
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE, IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE control, IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_device_get_connection_status_update, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE"
 - "IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE"
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
- IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</b> 
   IOCTL Gets a connection status update.


## -ioctlparameters




### -input-buffer

A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.


### -input-buffer-length

The size of a BOOL.


### -output-buffer

A BOOL that is the new connection status. TRUE if connected. FALSE if not connected.


### -output-buffer-length

The size of a BOOL.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If a request is already pending the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.


## -remarks



This request will complete immediately if the input parameter is TRUE or if the connection status has changed since the last request. Otherwise this request will remain pending until the connection status changes or the request is cancelled.

The audio driver sends this request to get the initial connection status, and sends subsequent requests to be updated when the status changes. The driver stores the connection status in appropriate context data.

When the request completes and indicates a change in the connection status, the audio driver generates the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-pincaps-jackinfochange">KSEVENT_PINCAPS_JACKINFOCHANGE</a> KS event.

When handling the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-jack-description">KSPROPERTY_JACK_DESCRIPTION</a> KS property, the audio driver sets the <i>IsConnected</i> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksjack-description">KSJACK_DESCRIPTION</a> structure based on the connection status.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-pincaps-jackinfochange">KSEVENT_PINCAPS_JACKINFOCHANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksjack-description">KSJACK_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-jack-description">KSPROPERTY_JACK_DESCRIPTION</a>
 

 

