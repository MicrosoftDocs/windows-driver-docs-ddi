---
UID: NI:bthhfpddi.IOCTL_BTHHFP_STREAM_CLOSE
title: IOCTL_BTHHFP_STREAM_CLOSE (bthhfpddi.h)
description: The IOCTL_BTHHFP_STREAM_CLOSE IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.
old-location: audio\ioctl_bthhfp_stream_close.htm
tech.root: audio
ms.assetid: 689296FA-E28A-4F9C-8E09-2CAC8A189808
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_STREAM_CLOSE IOCTL"]
ms.keywords: IOCTL_BTHHFP_STREAM_CLOSE, IOCTL_BTHHFP_STREAM_CLOSE control, IOCTL_BTHHFP_STREAM_CLOSE control code [Audio Devices], audio.ioctl_bthhfp_stream_close, bthhfpddi/IOCTL_BTHHFP_STREAM_CLOSE
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_BTHHFP_STREAM_CLOSE
 - bthhfpddi/IOCTL_BTHHFP_STREAM_CLOSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthhfpddi.h
api_name:
 - IOCTL_BTHHFP_STREAM_CLOSE
---

# IOCTL_BTHHFP_STREAM_CLOSE IOCTL


## -description

The <b>IOCTL_BTHHFP_STREAM_CLOSE</b> 
   IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.

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

The request completes immediately.

The audio driver starts this request when the KS pin transitions to the KSSTATE_STOP state, and should not finish the pin state transition until this request completes.

## -see-also

<a href="/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>