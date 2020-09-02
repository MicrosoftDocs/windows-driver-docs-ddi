---
UID: NF:sti.IStiDevice.LockDevice
title: IStiDevice::LockDevice (sti.h)
description: The IStiDevice::LockDevice method locks a device for exclusive use by the caller.
old-location: image\istidevice_lockdevice.htm
tech.root: image
ms.assetid: 208d9dc3-736b-4684-b8d3-802f6df78142
ms.date: 05/03/2018
keywords: ["IStiDevice::LockDevice"]
ms.keywords: IStiDevice interface [Imaging Devices],LockDevice method, IStiDevice.LockDevice, IStiDevice::LockDevice, LockDevice, LockDevice method [Imaging Devices], LockDevice method [Imaging Devices],IStiDevice interface, image.istidevice_lockdevice, sti/IStiDevice::LockDevice, stifnc_05519c97-dd77-4c30-836e-5b1991a5b3f7.xml
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
 - IStiDevice::LockDevice
 - sti/IStiDevice::LockDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.LockDevice
---

# IStiDevice::LockDevice


## -description

The <b>IStiDevice::LockDevice </b>method locks a device for exclusive use by the caller.

## -parameters

### -param dwTimeOut 

[in]
Caller-supplied time-out value, in milliseconds. If the lock is not obtained in this time period, an error is returned.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

Clients of the <b>IStiDevice</b> COM interface must call <b>IStiDevice::LockDevice</b> before calling the following methods:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-devicereset">IStiDevice::DeviceReset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-diagnostic">IStiDevice::Diagnostic</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-escape">IStiDevice::Escape</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getstatus">IStiDevice::GetStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawreadcommand">IStiDevice::RawReadCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawreaddata">IStiDevice::RawReadData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawwritecommand">IStiDevice::RawWriteCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawwritedata">IStiDevice::RawWriteData</a>


If the <b>IStiDevice::LockDevice</b> method is able to obtain an <b>IStiDevice</b>-level lock on the device within the specified time-out period, it then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-lockdevice">IStiUSD::LockDevice</a> in the appropriate vendor-supplied minidriver.

Each call to <b>IStiDevice::LockDevice</b> must be paired with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.

Before calling <b>IStiDevice::LockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

