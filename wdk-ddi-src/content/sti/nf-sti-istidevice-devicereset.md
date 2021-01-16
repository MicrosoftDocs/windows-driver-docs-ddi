---
UID: NF:sti.IStiDevice.DeviceReset
title: IStiDevice::DeviceReset (sti.h)
description: The IStiDevice::DeviceReset method resets a still image device to a known state.
old-location: image\istidevice_devicereset.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDevice::DeviceReset"]
ms.keywords: DeviceReset, DeviceReset method [Imaging Devices], DeviceReset method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],DeviceReset method, IStiDevice.DeviceReset, IStiDevice::DeviceReset, image.istidevice_devicereset, sti/IStiDevice::DeviceReset, stifnc_ef289b1a-3123-4e1e-b643-688a10e69e36.xml
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
 - IStiDevice::DeviceReset
 - sti/IStiDevice::DeviceReset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Sti.h
api_name:
 - IStiDevice::DeviceReset
---

# IStiDevice::DeviceReset


## -description

The <b>IStiDevice::DeviceReset</b> method resets a still image device to a known state.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::DeviceReset</b> method resets the device by calling <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-devicereset">IStiUSD::DeviceReset</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::DeviceReset</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::DeviceReset</b> must be preceded by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.

