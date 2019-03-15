---
UID: NF:stiusd.IStiUSD.UnLockDevice
title: IStiUSD::UnLockDevice (stiusd.h)
description: A still image minidriver's IStiUSD::UnLockDevice method unlocks a device that was locked by a previous call to IStiUSD::LockDevice.
old-location: image\istiusd_unlockdevice.htm
tech.root: image
ms.assetid: ae19ae38-3bca-42c8-8713-68bb161104b8
ms.date: 05/03/2018
ms.keywords: IStiUSD interface [Imaging Devices],UnLockDevice method, IStiUSD.UnLockDevice, IStiUSD::UnLockDevice, UnLockDevice, UnLockDevice method [Imaging Devices], UnLockDevice method [Imaging Devices],IStiUSD interface, image.istiusd_unlockdevice, stifnc_8c11e0a0-68ec-4556-ae40-6bed6b5b4831.xml, stiusd/IStiUSD::UnLockDevice
ms.topic: method
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Stiusd.h
api_name:
- IStiUSD.UnLockDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::UnLockDevice


## -description


A still image minidriver's <b>IStiUSD::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a>.


## -parameters






## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



If a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a> method called <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>, then <b>IStiUSD::UnlockDevice</b> should call <b>CloseHandle</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>
 

 

