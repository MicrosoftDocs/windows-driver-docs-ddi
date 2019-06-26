---
UID: NF:sti.IStiDevice.RawWriteData
title: IStiDevice::RawWriteData (sti.h)
description: The IStiDevice::RawWriteData method writes data to a still image device.
old-location: image\istidevice_rawwritedata.htm
tech.root: image
ms.assetid: bc64b3d6-8c86-4f99-b3b9-de31f576988c
ms.date: 05/03/2018
ms.keywords: IStiDevice interface [Imaging Devices],RawWriteData method, IStiDevice.RawWriteData, IStiDevice::RawWriteData, RawWriteData, RawWriteData method [Imaging Devices], RawWriteData method [Imaging Devices],IStiDevice interface, image.istidevice_rawwritedata, sti/IStiDevice::RawWriteData, stifnc_2b8739f4-3ab7-4b25-bae2-7e025cffe72d.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- sti.h
api_name:
- IStiDevice.RawWriteData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice::RawWriteData


## -description


The <b>IStiDevice::RawWriteData</b> method writes data to a still image device.


## -parameters




### -param lpBuffer [in]

Caller-supplied pointer to a buffer containing data to be sent to the device.


### -param nNumberOfBytes

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.


### -param lpOverlapped [in, optional]

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiDevice::RawWriteData</b> method calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-rawwritedata">IStiUSD::RawWriteData</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::RawWriteData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawWriteData</b> must be preceded by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStiDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-rawwritecommand">IStiDevice::RawWriteCommand</a>
 

 

