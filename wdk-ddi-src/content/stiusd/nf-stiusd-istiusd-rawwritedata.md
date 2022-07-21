---
UID: NF:stiusd.IStiUSD.RawWriteData
title: IStiUSD::RawWriteData (stiusd.h)
description: A still image minidriver's IStiUSD::RawWriteData method writes data to a still image device.
tech.root: image
ms.date: 04/19/2022
keywords: ["IStiUSD::RawWriteData"]
ms.keywords: IStiUSD interface [Imaging Devices],RawWriteData method, IStiUSD.RawWriteData, IStiUSD::RawWriteData, RawWriteData, RawWriteData method [Imaging Devices], RawWriteData method [Imaging Devices],IStiUSD interface, image.istiusd_rawwritedata, stifnc_32bdc55e-1e54-44ba-be36-e851d333f207.xml, stiusd/IStiUSD::RawWriteData
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
 - IStiUSD::RawWriteData
 - stiusd/IStiUSD::RawWriteData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD::RawWriteData
---

## -description

A still image minidriver's **IStiUSD::RawWriteData** method writes data to a still image device.

## -parameters

### -param lpBuffer

Caller-supplied pointer to a buffer containing data to be sent to the device.

### -param nNumberOfBytes

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by *lpBuffer*.

### -param lpOverlapped

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

A still image minidriver typically implements this method by calling **WriteFile** (described in the Windows SDK documentation).

## -see-also

[IStiDevice::RawWriteData](../sti/nf-sti-istidevice-rawwritedata.md)

[IStiUSD](../_image/index.md)