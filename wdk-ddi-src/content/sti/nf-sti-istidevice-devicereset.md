---
UID: NF:sti.IStiDevice.DeviceReset
title: IStiDevice::DeviceReset method
author: windows-driver-content
description: The IStiDevice::DeviceReset method resets a still image device to a known state.
old-location: image\istidevice_devicereset.htm
old-project: image
ms.assetid: 8a52c452-9a80-45d5-9bc8-85e17654eb6a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DeviceReset method [Imaging Devices], DeviceReset method [Imaging Devices], IStiDevice interface, DeviceReset,IStiDevice.DeviceReset, IStiDevice, IStiDevice interface [Imaging Devices], DeviceReset method, IStiDevice::DeviceReset, image.istidevice_devicereset, sti/IStiDevice::DeviceReset, stifnc_ef289b1a-3123-4e1e-b643-688a10e69e36.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Sti.h
api_name:
-	IStiDevice.DeviceReset
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::DeviceReset method


## -description


The <b>IStiDevice::DeviceReset</b> method resets a still image device to a known state.


## -syntax


````
HRESULT DeviceReset();
````


## -parameters






## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiDevice::DeviceReset</b> method resets the device by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543812">IStiUSD::DeviceReset</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::DeviceReset</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::DeviceReset</b> must be preceded by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a> and followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.



