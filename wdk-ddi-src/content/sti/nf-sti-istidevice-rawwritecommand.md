---
UID: NF:sti.IStiDevice.RawWriteCommand
title: IStiDevice::RawWriteCommand (sti.h)
description: The IStiDevice::RawWriteCommand method sends command information to a still image device.
old-location: image\istidevice_rawwritecommand.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDevice::RawWriteCommand"]
ms.keywords: IStiDevice interface [Imaging Devices],RawWriteCommand method, IStiDevice.RawWriteCommand, IStiDevice::RawWriteCommand, RawWriteCommand, RawWriteCommand method [Imaging Devices], RawWriteCommand method [Imaging Devices],IStiDevice interface, image.istidevice_rawwritecommand, sti/IStiDevice::RawWriteCommand, stifnc_07c4667c-956f-4396-bc59-0bcbf21103a8.xml
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
 - IStiDevice::RawWriteCommand
 - sti/IStiDevice::RawWriteCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice::RawWriteCommand
---

# IStiDevice::RawWriteCommand


## -description

The <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

## -parameters

### -param lpBuffer 

[in]
Caller-supplied pointer to a buffer containing data to be sent to the device.

### -param nNumberOfBytes

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.

### -param lpOverlapped 

[in, optional]
Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::RawWriteCommand</b> method calls <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawwritecommand">IStiUSD::RawWriteCommand</a>, which is exported by vendor-supplied minidrivers. The meaning of buffer contents are vendor-defined.

It is only necessary to call <b>IStiDevice::RawWriteCommand</b> if commands and data are written to a device by different methods. For other devices, <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawwritedata">IStiDevice::RawWriteData</a> can be used for both commands and data.

Before calling <b>IStiDevice::RawWriteCommand</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawWriteCommand</b> must be preceded by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.

