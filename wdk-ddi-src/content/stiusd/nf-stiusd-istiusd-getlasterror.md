---
UID: NF:stiusd.IStiUSD.GetLastError
title: IStiUSD::GetLastError method
author: windows-driver-content
description: The IStiUSD::GetLastError method returns the last known error associated with a still image device.
old-location: image\istiusd_getlasterror.htm
old-project: image
ms.assetid: a7f265b8-c8a9-4a79-85e2-e3f52bf25f31
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, D, E, G, GetLastError method [Imaging Devices], GetLastError method [Imaging Devices], IStiUSD interface, GetLastError,IStiUSD.GetLastError, I, IStiUSD, IStiUSD interface [Imaging Devices], GetLastError method, IStiUSD::GetLastError, L, S, U, a, e, i, image.istiusd_getlasterror, o, r, s, stifnc_fad89b49-ff86-4a75-bae4-0aae22d9f5d6.xml, stiusd/IStiUSD::GetLastError, t"
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
req.lib: stiusd.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	stiusd.h
apiname:
-	IStiUSD.GetLastError
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::GetLastError method


## -description


The <b>IStiUSD::GetLastError</b> method returns the last known error associated with a still image device.


## -syntax


````
HRESULT GetLastError(
   LPDWORD pdwLastDeviceError
);
````


## -parameters




### -param pdwLastDeviceError

Caller-supplied pointer to a buffer in which the error code will be stored.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543747">IStiDevice::GetLastError</a>



<a href="..\stiusd\nn-stiusd-istiusd.md">IStiUSD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::GetLastError method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

