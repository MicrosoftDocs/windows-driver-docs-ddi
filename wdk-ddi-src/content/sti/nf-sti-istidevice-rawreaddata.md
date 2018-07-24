---
UID: NF:sti.IStiDevice.RawReadData
title: IStiDevice::RawReadData
author: windows-driver-content
description: The IStiDevice::RawReadData method reads data from a still image device.
old-location: image\istidevice_rawreaddata.htm
tech.root: image
ms.assetid: b4510fac-839b-4744-9525-2bf96c5c724e
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IStiDevice interface [Imaging Devices],RawReadData method, IStiDevice.RawReadData, IStiDevice::RawReadData, RawReadData, RawReadData method [Imaging Devices], RawReadData method [Imaging Devices],IStiDevice interface, image.istidevice_rawreaddata, sti/IStiDevice::RawReadData, stifnc_cbd37004-cf03-4a49-9422-374e01abe376.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	sti.h
api_name:
-	IStiDevice.RawReadData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice::RawReadData


## -description


The <b>IStiDevice::RawReadData</b> method reads data from a still image device.


## -parameters




### -param lpBuffer [in, out]

Caller-supplied pointer to a buffer to receive data read from the device.


### -param lpdwNumberOfBytes [in, out]

Caller-supplied pointer to a DWORD. The caller must load the DWORD with the number of bytes in the buffer pointed to by <i>lpBuffer</i>. On return, it will contain the number of bytes actually read.


### -param lpOverlapped [in, optional]

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiDevice::RawReadData</b> method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543834">IStiUSD::RawReadData</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::RawReadData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawReadData</b> must be preceded by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a> and followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.




## -see-also




<a href="https://msdn.microsoft.com/86ce412e-007b-4ea9-9c09-766eee543852">IStiDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>
 

 

