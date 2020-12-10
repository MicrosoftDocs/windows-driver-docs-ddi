---
UID: NF:sti.IStiDevice.GetLastError
title: IStiDevice::GetLastError (sti.h)
description: The IStiDevice::GetLastError method returns the last known error associated with a still image device.
old-location: image\istidevice_getlasterror.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDevice::GetLastError"]
ms.keywords: GetLastError, GetLastError method [Imaging Devices], GetLastError method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetLastError method, IStiDevice.GetLastError, IStiDevice::GetLastError, image.istidevice_getlasterror, sti/IStiDevice::GetLastError, stifnc_9c8050a1-8e9a-4b24-a461-bc567602900d.xml
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
 - IStiDevice::GetLastError
 - sti/IStiDevice::GetLastError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.GetLastError
---

# IStiDevice::GetLastError


## -description

The <b>IStiDevice::GetLastError</b> method returns the last known error associated with a still image device.

## -parameters

### -param pdwLastDeviceError 

[out]
Caller-supplied pointer to a buffer in which the error code will be stored.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

Before calling IStiDevice::GetLastError, clients of the IStiDevice COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an IStiDevice interface pointer, which provides access to a specified device.
