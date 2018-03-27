---
UID: NF:stiusd.IStiUSD.Escape
title: IStiUSD::Escape method
author: windows-driver-content
description: A still image minidriver's IStiUSD::Escape method performs a vendor-specific I/O operation on a still image device.
old-location: image\istiusd_escape.htm
old-project: image
ms.assetid: 9129e776-b5d0-4f53-b2be-67e593369c6c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: Escape method [Imaging Devices], Escape method [Imaging Devices], IStiUSD interface, Escape,IStiUSD.Escape, IStiUSD, IStiUSD interface [Imaging Devices], Escape method, IStiUSD::Escape, image.istiusd_escape, stifnc_74a53282-ebd8-4c87-97b1-58195b40a1af.xml, stiusd/IStiUSD::Escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	stiusd.h
api_name:
-	IStiUSD.Escape
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::Escape method


## -description


A still image minidriver's <b>IStiUSD::Escape</b> method performs a vendor-specific I/O operation on a still image device.


## -parameters




### -param EscapeFunction

Caller-supplied, vendor-defined, DWORD-sized value representing an I/O operation. Vendor-defined values must be greater than STI_RAW_RESERVED, which is defined in <i>Sti.h</i>.


### -param lpInData

Caller-supplied pointer to a buffer containing data sent to the device.


### -param cbInDataSize

Caller-supplied length, in bytes, of the buffer pointed to by <i>lpInData</i>.


### -param pOutData

Caller-supplied pointer to a memory buffer to receive data from the device.


### -param cbOutDataSize




### -param pdwActualData

Receives the number of bytes actually written to <i>pOutData</i>.


#### - dwOutDataSize

Caller-supplied length, in bytes, of the buffer pointed to by <i>lpOutData</i>.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>. If the method is not implemented, it should return STIERR_UNSUPPORTED.




## -remarks



A still image minidriver only needs to implement <b>IStiUSD::Escape</b> if I/O operations are required that cannot be implemented within <a href="https://msdn.microsoft.com/library/windows/hardware/ff543834">IStiUSD::RawReadData</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543839">IStiUSD::RawWriteData</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543831">IStiUSD::RawReadCommand</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543836">IStiUSD::RawWriteCommand</a> methods. The minidriver defines parameter usage for <b>IStiUSD::Escape</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::Escape method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

