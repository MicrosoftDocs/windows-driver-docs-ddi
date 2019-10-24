---
UID: NF:stiusd.IStiUSD.RawReadData
title: IStiUSD::RawReadData (stiusd.h)
description: A still image minidriver's IStiUSD::RawReadData method reads data from a still image device.
old-location: image\istiusd_rawreaddata.htm
tech.root: image
ms.assetid: 6ae64309-da53-420b-bf87-e8924e902dba
ms.date: 05/03/2018
ms.keywords: IStiUSD interface [Imaging Devices],RawReadData method, IStiUSD.RawReadData, IStiUSD::RawReadData, RawReadData, RawReadData method [Imaging Devices], RawReadData method [Imaging Devices],IStiUSD interface, image.istiusd_rawreaddata, stifnc_29a3d9c4-92a8-47cd-b12c-0280003c43b7.xml, stiusd/IStiUSD::RawReadData
ms.topic: method
f1_keywords:
 - "stiusd/IStiUSD.RawReadData"
req.header: stiusd.h
req.include-header: Stiusd.h
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
- stiusd.h
api_name:
- IStiUSD.RawReadData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::RawReadData


## -description


A still image minidriver's <b>IStiUSD::RawReadData</b> method reads data from a still image device.


## -parameters




### -param lpBuffer

Caller-supplied pointer to a buffer to receive data read from the device.


### -param lpdwNumberOfBytes

Caller-supplied pointer to a DWORD. The caller loads the DWORD with the number of bytes in the buffer pointed to by <i>lpBuffer</i>. The driver must replace this value with the number of bytes actually read.


### -param lpOverlapped

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



A still image minidriver typically implements this method by calling <b>ReadFile</b> (described in the Windows SDK documentation).

For USB devices, better performance can be achieved if read requests are aligned to maximum packet size boundaries. Maximum packet sizes can be obtained by calling <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, specifying the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_get_channel_align_rqst">IOCTL_GET_CHANNEL_ALIGN_RQST</a> I/O control code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawreaddata">IStiDevice::RawReadData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>
 

 

