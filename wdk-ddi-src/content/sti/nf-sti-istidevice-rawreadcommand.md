---
UID: NF:sti.IStiDevice.RawReadCommand
title: IStiDevice::RawReadCommand method
author: windows-driver-content
description: The IStiDevice::RawReadCommand method reads command information from a still image device.
old-location: image\istidevice_rawreadcommand.htm
old-project: image
ms.assetid: fc6b46af-d3e3-4a49-a354-c0effee6a005
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: sti/IStiDevice::RawReadCommand, IStiDevice interface [Imaging Devices], RawReadCommand method, IStiDevice, IStiDevice::RawReadCommand, RawReadCommand method [Imaging Devices], RawReadCommand method [Imaging Devices], IStiDevice interface, RawReadCommand, image.istidevice_rawreadcommand, stifnc_cdfe25e7-b5c4-4ed0-b8f5-363c83f1bbba.xml
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
-	IStiDevice.RawReadCommand
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::RawReadCommand method


## -description


The <b>IStiDevice::RawReadCommand</b> method reads command information from a still image device.


## -syntax


````
HRESULT RawReadCommand(
  [in, out]      LPVOID       lpBuffer,
  [in, out]      LPDWORD      lpdwNumberOfBytes,
  [in, optional] LPOVERLAPPED lpOverlapped
);
````


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


The <b>IStiDevice::RawReadCommand</b> method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543831">IStiUSD::RawReadCommand</a>, which is exported by vendor-supplied minidrivers. The meaning of buffer contents are vendor-defined.

It is only necessary to call <b>IStiDevice::RawReadCommand</b> if command and data information are read from a device by different methods. For other devices, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a> can be used for both commands and data.

Before calling <b>IStiDevice::RawReadCommand</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawReadCommand</b> must be preceded by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a> and followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.


