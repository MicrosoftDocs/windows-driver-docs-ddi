---
UID: NF:sti.IStiDevice.GetLastErrorInfo
title: IStiDevice::GetLastErrorInfo (sti.h)
description: The IStiDevice::GetLastErrorInfo method returns information about the last known error associated with a still image device.
tech.root: image
ms.date: 04/18/2022
keywords: ["IStiDevice::GetLastErrorInfo"]
ms.keywords: GetLastErrorInfo, GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetLastErrorInfo method, IStiDevice.GetLastErrorInfo, IStiDevice::GetLastErrorInfo, image.istidevice_getlasterrorinfo, sti/IStiDevice::GetLastErrorInfo, stifnc_f54b574c-5894-4029-888c-fe60738858d7.xml
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
 - IStiDevice::GetLastErrorInfo
 - sti/IStiDevice::GetLastErrorInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice::GetLastErrorInfo
---

## -description

The **IStiDevice::GetLastErrorInfo** method returns information about the last known error associated with a still image device.

## -parameters

### -param pLastErrorInfo [out]

Caller-supplied pointer to an [STI_ERROR_INFO](./ns-sti-_error_infow.md) structure to receive error information.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h<*.

## -remarks

The **IStiDevice::GetLastErrorInfo** method returns information about the most recent error by filling in the caller-supplied [STI_ERROR_INFO](./ns-sti-_error_infow.md) structure. The method calls [IStiUSD::GetLastErrorInfo](../stiusd/nf-stiusd-istiusd-getlasterrorinfo.md), which is exported by vendor-supplied minidrivers.

Before calling **IStiDevice::GetLastErrorInfo**, clients of the **IStiDevice** COM interface must call [IStillImage::CreateDevice](/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)) to obtain an **IStiDevice** interface pointer, which provides access to a specified device.