---
UID: NF:sti.IStiDevice.GetStatus
title: IStiDevice::GetStatus (sti.h)
description: The IStiDevice::GetStatus method returns a still image device's status information.
old-location: image\istidevice_getstatus.htm
tech.root: image
ms.assetid: e9539565-e13f-42ea-9566-066e2c9ae2ae
ms.date: 05/03/2018
keywords: ["IStiDevice::GetStatus"]
ms.keywords: GetStatus, GetStatus method [Imaging Devices], GetStatus method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetStatus method, IStiDevice.GetStatus, IStiDevice::GetStatus, image.istidevice_getstatus, sti/IStiDevice::GetStatus, stifnc_b1ed4e70-9658-47e4-9f89-6dc2b8463886.xml
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
 - IStiDevice::GetStatus
 - sti/IStiDevice::GetStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.GetStatus
---

# IStiDevice::GetStatus


## -description

The <b>IStiDevice::GetStatus</b> method returns a still image device's status information.

## -parameters

### -param pDevStatus 

[in, out]
Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_device_status">STI_DEVICE_STATUS</a> structure. The caller must set the <b>dwSize</b> and <b>StatusMask</b> members.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::GetStatus</b> method returns device status information in the caller-supplied <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_device_status">STI_DEVICE_STATUS</a> structure. It obtains the status by calling <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getstatus">IStiUSD::GetStatus</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::GetStatus</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::GetStatus</b> must be preceded by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.