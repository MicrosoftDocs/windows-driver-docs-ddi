---
UID: NF:stiusd.IStiUSD.GetLastError
title: IStiUSD::GetLastError (stiusd.h)
description: The IStiUSD::GetLastError method returns the last known error associated with a still image device.
old-location: image\istiusd_getlasterror.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiUSD::GetLastError"]
ms.keywords: GetLastError, GetLastError method [Imaging Devices], GetLastError method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],GetLastError method, IStiUSD.GetLastError, IStiUSD::GetLastError, image.istiusd_getlasterror, stifnc_fad89b49-ff86-4a75-bae4-0aae22d9f5d6.xml, stiusd/IStiUSD::GetLastError
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
 - IStiUSD::GetLastError
 - stiusd/IStiUSD::GetLastError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD.GetLastError
---

# IStiUSD::GetLastError


## -description

The <b>IStiUSD::GetLastError</b> method returns the last known error associated with a still image device.

## -parameters

### -param pdwLastDeviceError

Caller-supplied pointer to a buffer in which the error code will be stored.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlasterror">IStiDevice::GetLastError</a>



<a href="/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>
