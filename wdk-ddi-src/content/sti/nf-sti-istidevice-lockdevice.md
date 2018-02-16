---
UID: NF:sti.IStiDevice.LockDevice
title: IStiDevice::LockDevice method
author: windows-driver-content
description: The IStiDevice::LockDevice method locks a device for exclusive use by the caller.
old-location: image\istidevice_lockdevice.htm
old-project: image
ms.assetid: 208d9dc3-736b-4684-b8d3-802f6df78142
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IStiDevice::LockDevice, image.istidevice_lockdevice, LockDevice method [Imaging Devices], IStiDevice interface, sti/IStiDevice::LockDevice, IStiDevice interface [Imaging Devices], LockDevice method, LockDevice, LockDevice method [Imaging Devices], IStiDevice, stifnc_05519c97-dd77-4c30-836e-5b1991a5b3f7.xml
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
-	sti.h
apiname:
-	IStiDevice.LockDevice
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::LockDevice method


## -description


The <b>IStiDevice::LockDevice </b>method locks a device for exclusive use by the caller.


## -syntax


````
HRESULT LockDevice(
  [in] DWORD dwTimeOut
);
````


## -parameters




### -param dwTimeOut [in]

Caller-supplied time-out value, in milliseconds. If the lock is not obtained in this time period, an error is returned.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



Clients of the <b>IStiDevice</b> COM interface must call <b>IStiDevice::LockDevice</b> before calling the following methods:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>


If the <b>IStiDevice::LockDevice</b> method is able to obtain an <b>IStiDevice</b>-level lock on the device within the specified time-out period, it then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a> in the appropriate vendor-supplied minidriver.

Each call to <b>IStiDevice::LockDevice</b> must be paired with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.

Before calling <b>IStiDevice::LockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.



