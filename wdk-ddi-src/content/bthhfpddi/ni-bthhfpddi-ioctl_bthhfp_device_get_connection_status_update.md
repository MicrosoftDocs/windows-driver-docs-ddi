---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
title: IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL Gets a connection status update.
old-location: audio\ioctl_bthhfp_device_get_connection_status_update.htm
old-project: audio
ms.assetid: 19863998-99AB-427E-BFBD-B8EF42C74DEF
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE, IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE control, IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE control code [Audio Devices], audio.ioctl_bthhfp_device_get_connection_status_update, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE
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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If a request is already pending the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.


## -remarks



This request will complete immediately if the input parameter is TRUE or if the connection status has changed since the last request. Otherwise this request will remain pending until the connection status changes or the request is cancelled.

The audio driver sends this request to get the initial connection status, and sends subsequent requests to be updated when the status changes. The driver stores the connection status in appropriate context data.

When the request completes and indicates a change in the connection status, the audio driver generates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537134">KSEVENT_PINCAPS_JACKINFOCHANGE</a> KS event.

When handling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537364">KSPROPERTY_JACK_DESCRIPTION</a> KS property, the audio driver sets the <i>IsConnected</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537136">KSJACK_DESCRIPTION</a> structure based on the connection status.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537134">KSEVENT_PINCAPS_JACKINFOCHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537136">KSJACK_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537364">KSPROPERTY_JACK_DESCRIPTION</a>
 

 

