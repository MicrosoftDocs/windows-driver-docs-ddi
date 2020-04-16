---
UID: NF:stiusd.IStiUSD.RawWriteData
title: IStiUSD::RawWriteData (stiusd.h)
description: A still image minidriver's IStiUSD::RawWriteData method writes data to a still image device.
old-location: image\istiusd_rawwritedata.htm
tech.root: image
ms.assetid: 82700669-b98f-486c-a7a6-cd7138300f11
ms.date: 05/03/2018
keywords: ["IStiUSD::RawWriteData"]
ms.keywords: IStiUSD interface [Imaging Devices],RawWriteData method, IStiUSD.RawWriteData, IStiUSD::RawWriteData, RawWriteData, RawWriteData method [Imaging Devices], RawWriteData method [Imaging Devices],IStiUSD interface, image.istiusd_rawwritedata, stifnc_32bdc55e-1e54-44ba-be36-e851d333f207.xml, stiusd/IStiUSD::RawWriteData
f1_keywords:
 - "stiusd/IStiUSD.RawWriteData"
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
- IStiUSD.RawWriteData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::RawWriteData


## -description


A still image minidriver's <b>IStiUSD::RawWriteData</b> method writes data to a still image device.


## -parameters




### -param lpBuffer

Caller-supplied pointer to a buffer containing data to be sent to the device.


### -param nNumberOfBytes




### -param lpOverlapped

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


#### - dwNumberOfBytes

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



A still image minidriver typically implements this method by calling <b>WriteFile</b> (described in the Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawwritedata">IStiDevice::RawWriteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>
 

 

