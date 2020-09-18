---
UID: NF:stiusd.IStiUSD.UnLockDevice
title: IStiUSD::UnLockDevice (stiusd.h)
description: A still image minidriver's IStiUSD::UnLockDevice method unlocks a device that was locked by a previous call to IStiUSD::LockDevice.
old-location: image\istiusd_unlockdevice.htm
tech.root: image
ms.assetid: ae19ae38-3bca-42c8-8713-68bb161104b8
ms.date: 05/03/2018
keywords: ["IStiUSD::UnLockDevice"]
ms.keywords: IStiUSD interface [Imaging Devices],UnLockDevice method, IStiUSD.UnLockDevice, IStiUSD::UnLockDevice, UnLockDevice, UnLockDevice method [Imaging Devices], UnLockDevice method [Imaging Devices],IStiUSD interface, image.istiusd_unlockdevice, stifnc_8c11e0a0-68ec-4556-ae40-6bed6b5b4831.xml, stiusd/IStiUSD::UnLockDevice
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
 - IStiUSD::UnLockDevice
 - stiusd/IStiUSD::UnLockDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Stiusd.h
api_name:
 - IStiUSD.UnLockDevice
---

# IStiUSD::UnLockDevice


## -description

A still image minidriver's <b>IStiUSD::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-lockdevice">IStiUSD::LockDevice</a>.

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

If a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-lockdevice">IStiUSD::LockDevice</a> method called <a href="https://docs.microsoft.com/windows/win32/api/fileapi/nf-fileapi-createfilea">CreateFile</a>, then <b>IStiUSD::UnlockDevice</b> should call <b>CloseHandle</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>

