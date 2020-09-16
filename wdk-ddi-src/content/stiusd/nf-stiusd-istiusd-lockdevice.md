---
UID: NF:stiusd.IStiUSD.LockDevice
title: IStiUSD::LockDevice (stiusd.h)
description: A still image minidriver's IStiUSD::LockDevice method locks a device for exclusive use by the caller.
old-location: image\istiusd_lockdevice.htm
tech.root: image
ms.assetid: cb91ef14-53d7-42fa-b3e5-54eb3b0925b8
ms.date: 05/03/2018
keywords: ["IStiUSD::LockDevice"]
ms.keywords: IStiUSD interface [Imaging Devices],LockDevice method, IStiUSD.LockDevice, IStiUSD::LockDevice, LockDevice, LockDevice method [Imaging Devices], LockDevice method [Imaging Devices],IStiUSD interface, image.istiusd_lockdevice, stifnc_147be8d0-9e2a-4ade-99ce-36c7f3a8adeb.xml, stiusd/IStiUSD::LockDevice
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
 - IStiUSD::LockDevice
 - stiusd/IStiUSD::LockDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Stiusd.h
api_name:
 - IStiUSD.LockDevice
---

# IStiUSD::LockDevice


## -description

A still image minidriver's <b>IStiUSD::LockDevice</b> method locks a device for exclusive use by the caller.

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

If you are writing a driver for a device connected to a serial port, you might want to call <a href="https://docs.microsoft.com/windows/win32/api/fileapi/nf-fileapi-createfilea">CreateFile</a> from within the driver's <b>IStiUSD::LockDevice</b> method if the device was opened in status mode. This will prohibit other applications from using the port (which might be supporting other devices) while status information is being obtained. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/transfer-modes">Transfer Modes</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>

