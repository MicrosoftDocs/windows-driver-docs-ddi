---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_connect.htm
old-project: audio
ms.assetid: CE591873-FFDC-49A2-BB75-FE445338D633
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT, IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT control code [Audio Devices], audio.ioctl_bthhfp_device_request_connect, bthhfpddi/IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
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
-	IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

N/A


## -remarks



This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.

The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a>



 

 


