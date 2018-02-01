---
UID: NF:stiusd.IStiUSD.DeviceReset
title: IStiUSD::DeviceReset method
author: windows-driver-content
description: A still image minidriver's IStiUSD::DeviceReset method resets a still image device to a known, initialized state.
old-location: image\istiusd_devicereset.htm
old-project: image
ms.assetid: f6944297-9aca-4912-a398-c5f3a3e8d4b4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IStiUSD::DeviceReset, IStiUSD, image.istiusd_devicereset, stiusd/IStiUSD::DeviceReset, IStiUSD interface [Imaging Devices], DeviceReset method, DeviceReset method [Imaging Devices], IStiUSD interface, DeviceReset, DeviceReset method [Imaging Devices], stifnc_94561ed6-1f7a-411e-b699-37d56165b2f7.xml
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
-	Stiusd.h
apiname:
-	IStiUSD.DeviceReset
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::DeviceReset method


## -description


A still image minidriver's <b>IStiUSD::DeviceReset</b> method resets a still image device to a known, initialized state.


## -syntax


````
STDMETHODIMP DeviceReset();
````


## -parameters





## -returns


If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::DeviceReset method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

