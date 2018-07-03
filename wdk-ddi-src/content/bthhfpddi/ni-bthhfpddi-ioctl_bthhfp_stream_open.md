---
UID: NI:bthhfpddi.IOCTL_BTHHFP_STREAM_OPEN
title: IOCTL_BTHHFP_STREAM_OPEN
author: windows-driver-content
description: The IOCTL_BTHHFP_STREAM_OPEN IOCTL requests an open synchronous connection-oriented (SCO) channel to transmit audio data over the air.
old-location: audio\ioctl_bthhfp_stream_open.htm
old-project: audio
ms.assetid: 67F42694-C6E1-458E-AE5F-7E3678F55A8B
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_BTHHFP_STREAM_OPEN, IOCTL_BTHHFP_STREAM_OPEN control, IOCTL_BTHHFP_STREAM_OPEN control code [Audio Devices], audio.ioctl_bthhfp_stream_open, bthhfpddi/IOCTL_BTHHFP_STREAM_OPEN
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
-	IOCTL_BTHHFP_STREAM_OPEN
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_STREAM_OPEN IOCTL


## -description


The <b>IOCTL_BTHHFP_STREAM_OPEN</b> 
   IOCTL requests an open synchronous connection-oriented (SCO) channel to transmit audio data over the air.


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

A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.


## -remarks



This request can remain pending for several seconds while resources are established.

While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>
 

 

