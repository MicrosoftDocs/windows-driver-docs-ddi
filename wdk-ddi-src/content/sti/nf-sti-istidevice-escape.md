---
UID: NF:sti.IStiDevice.Escape
title: IStiDevice::Escape (sti.h)
description: The IStiDevice::Escape method sends a request for a vendor-specific I/O operation to a still image device.
old-location: image\istidevice_escape.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDevice::Escape"]
ms.keywords: Escape, Escape method [Imaging Devices], Escape method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],Escape method, IStiDevice.Escape, IStiDevice::Escape, image.istidevice_escape, sti/IStiDevice::Escape, stifnc_5eb8e67e-67cc-4d04-abff-ada5b42b0004.xml
req.header: sti.h
req.include-header: Sti.h
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
 - IStiDevice::Escape
 - sti/IStiDevice::Escape
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.Escape
---

# IStiDevice::Escape


## -description

The <b>IStiDevice::Escape</b> method sends a request for a vendor-specific I/O operation to a still image device.

## -parameters

### -param EscapeFunction 

[in]
Caller-supplied, vendor-defined, DWORD-sized value representing an I/O operation. The device's minidriver must recognize this value and must export an <b>IStiUSD</b> interface. Vendor-defined values must be greater than STI_RAW_RESERVED, which is defined in <i>Sti.h</i>.

### -param lpInData 

[in]
Caller-supplied pointer to a buffer containing data to be sent to the device.

### -param cbInDataSize

Caller-supplied length, in bytes, of the data contained in the buffer pointed to by <i>lpInData</i>.

### -param pOutData 

[in, out]
Caller-supplied pointer to a memory buffer to receive data from the device.

### -param dwOutDataSize

Caller-supplied length, in bytes, of the buffer pointed to by <i>lpOutData</i>.

### -param pdwActualData 

[out]
Receives the number of bytes actually written to <i>pOutData</i>.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::Escape</b> method calls <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-escape">IStiUSD::Escape</a>, which is exported by vendor-supplied minidrivers. The device's minidriver defines the Method parameter usage.

Before calling <b>IStiDevice::Escape</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::Escape</b> must be preceded by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.
