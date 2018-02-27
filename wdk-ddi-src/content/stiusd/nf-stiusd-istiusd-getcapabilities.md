---
UID: NF:stiusd.IStiUSD.GetCapabilities
title: IStiUSD::GetCapabilities method
author: windows-driver-content
description: A still image minidriver's IStiUSD::GetCapabilities method returns a still image device's capabilities.
old-location: image\istiusd_getcapabilities.htm
old-project: image
ms.assetid: baec1e38-360e-4f4f-82bd-bc89e3f8483d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetCapabilities method [Imaging Devices], GetCapabilities method [Imaging Devices], IStiUSD interface, GetCapabilities,IStiUSD.GetCapabilities, IStiUSD, IStiUSD interface [Imaging Devices], GetCapabilities method, IStiUSD::GetCapabilities, image.istiusd_getcapabilities, stifnc_e0343c50-7695-417f-9742-1acd66f2791f.xml, stiusd/IStiUSD::GetCapabilities
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
-	IStiUSD.GetCapabilities
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::GetCapabilities method


## -description


A still image minidriver's <b>IStiUSD::GetCapabilities</b> method returns a still image device's capabilities.


## -syntax


````
HRESULT GetCapabilities(
   PSTI_USD_CAPS pUsdCaps
);
````


## -parameters




### -param pDevCaps






#### - pUsdCaps

Caller-supplied pointer to an empty <a href="..\stiusd\ns-stiusd-_sti_usd_caps.md">STI_USD_CAPS</a> structure.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiUSD::GetCapabilities</b> method should set appropriate device capability flags in the caller-supplied <a href="..\stiusd\ns-stiusd-_sti_usd_caps.md">STI_USD_CAPS</a> structure. It should also set the version number to STI_VERSION.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543745">IStiDevice::GetCapabilities</a>



<a href="..\stiusd\nn-stiusd-istiusd.md">IStiUSD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::GetCapabilities method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

