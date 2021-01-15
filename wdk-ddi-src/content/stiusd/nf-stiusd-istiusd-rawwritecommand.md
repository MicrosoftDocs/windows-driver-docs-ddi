---
UID: NF:stiusd.IStiUSD.RawWriteCommand
title: IStiUSD::RawWriteCommand (stiusd.h)
description: A still image minidriver's IStiDevice::RawWriteCommand method sends command information to a still image device.
old-location: image\istiusd_rawwritecommand.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiUSD::RawWriteCommand"]
ms.keywords: IStiUSD interface [Imaging Devices],RawWriteCommand method, IStiUSD.RawWriteCommand, IStiUSD::RawWriteCommand, RawWriteCommand, RawWriteCommand method [Imaging Devices], RawWriteCommand method [Imaging Devices],IStiUSD interface, image.istiusd_rawwritecommand, stifnc_508a67c1-4f4f-4324-bbb4-fc095fa023c4.xml, stiusd/IStiUSD::RawWriteCommand
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - IStiUSD::RawWriteCommand
 - stiusd/IStiUSD::RawWriteCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD::RawWriteCommand
---

# IStiUSD::RawWriteCommand


## -description

A still image minidriver's <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

## -parameters

### -param lpBuffer

Caller-supplied pointer to a buffer containing data to be sent to the device.

### -param nNumberOfBytes

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.

### -param lpOverlapped

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

It is only necessary to call <b>IStiUSD::RawWriteCommand</b> if commands and data are written to a device by different methods. For other devices, <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawwritedata">IStiUSD::RawWriteData</a> can be used for both commands and data. If the call is not implemented, it must return STIERR_UNSUPPORTED.

Implementation of this method, along with the meaning of buffer contents, are vendor-defined.

## -see-also

<a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawwritecommand">IStiDevice::RawWriteCommand</a>



<a href="/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>

