---
UID: NF:sti.IStiDevice.UnLockDevice
title: IStiDevice::UnLockDevice method
author: windows-driver-content
description: The IStiDevice::UnLockDevice method unlocks a device that was locked by a previous call to IStiDevice::LockDevice.
old-location: image\istidevice_unlockdevice.htm
old-project: image
ms.assetid: 0bcd48c6-be8a-47af-9e34-a06ce572925c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IStiDevice::UnLockDevice, UnLockDevice, image.istidevice_unlockdevice, IStiDevice, UnLockDevice method [Imaging Devices], IStiDevice interface [Imaging Devices], UnLockDevice method, stifnc_7f72c1a7-41cd-4191-8c8f-390dfc991246.xml, UnLockDevice method [Imaging Devices], IStiDevice interface, sti/IStiDevice::UnLockDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Sti.h
apiname:
-	IStiDevice.UnLockDevice
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::UnLockDevice method


## -description


The <b>IStiDevice::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a>.


## -syntax


````
HRESULT UnLockDevice();
````


## -parameters





## -returns


If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -remarks


Before the <b>IStiDevice::UnLockDevice</b> method releases the <b>IStiDevice</b>-level lock on the device, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543843">IStiUSD::UnLockDevice</a> in the appropriate vendor-supplied minidriver.

Before calling <b>IStiDevice::UnLockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.


