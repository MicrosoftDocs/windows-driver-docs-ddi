---
UID: NF:sti.IStiDevice.GetLastError
title: IStiDevice::GetLastError method
author: windows-driver-content
description: The IStiDevice::GetLastError method returns the last known error associated with a still image device.
old-location: image\istidevice_getlasterror.htm
old-project: image
ms.assetid: 20ad609d-454a-4d43-a58e-184cbb8e8da7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetLastError method [Imaging Devices], IStiDevice interface, sti/IStiDevice::GetLastError, IStiDevice::GetLastError, image.istidevice_getlasterror, IStiDevice, GetLastError, IStiDevice interface [Imaging Devices], GetLastError method, stifnc_9c8050a1-8e9a-4b24-a461-bc567602900d.xml, GetLastError method [Imaging Devices]
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
-	IStiDevice.GetLastError
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::GetLastError method


## -description


The <b>IStiDevice::GetLastError</b> method returns the last known error associated with a still image device.


## -syntax


````
HRESULT GetLastError(
  [out] LPDWORD pdwLastDeviceError
);
````


## -parameters




#### - pdwLastDeviceError [out]

Caller-supplied pointer to a buffer in which the error code will be stored.


## -returns


If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -remarks


Before calling IStiDevice::GetLastError, clients of the IStiDevice COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an IStiDevice interface pointer, which provides access to a specified device.


