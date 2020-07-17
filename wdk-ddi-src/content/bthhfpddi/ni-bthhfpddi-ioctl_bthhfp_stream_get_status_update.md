---
UID: NI:bthhfpddi.IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
title: IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE (bthhfpddi.h)
description: The IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL Gets a stream channel status update.
old-location: audio\ioctl_bthhfp_stream_get_status_update.htm
tech.root: audio
ms.assetid: 1D591422-4ED4-41B9-92E0-189A5EABE7D0
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL"]
ms.keywords: IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE, IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE control, IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_stream_get_status_update, bthhfpddi/IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE"
 - "IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE"
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
- IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL


## -description


The <b>IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE</b> 
   IOCTL Gets a stream channel status update.


## -ioctlparameters




### -input-buffer

A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.


### -input-buffer-length

The size of a BOOL.


### -output-buffer

An NT_STATUS value that represents the new stream channel status. An error status indicates that the synchronous connection-oriented (SCO) channel associated with the stream has been closed, and cannot be reestablished.


### -output-buffer-length

The size of an NT_STATUS object.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.

If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.


## -remarks



This request will complete immediately if the input parameter is TRUE or if the stream channel status has changed since the last request. Otherwise this request will remain pending until the stream channel status changes or the request is cancelled.

This request is valid only between a successful <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_stream_open">IOCTL_BTHHFP_STREAM_OPEN</a> request and subsequent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_stream_close">IOCTL_BTHHFP_STREAM_CLOSE</a> request. If this request is pending when the stream is closed by an <b>IOCTL_BTHHFP_STREAM_CLOSE</b> request, then the pending request is cancelled.

An error status can occur when the Bluetooth link is dropped or other similar conditions occur. Although such conditions are rare, the audio driver must be developed to handle them. This error status can often occur almost simultaneously with a connection status change to FALSE. However the audio driver should not rely on this change of status as a way to determine whether or not the Bluetooth link has been dropped.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>
 

 

