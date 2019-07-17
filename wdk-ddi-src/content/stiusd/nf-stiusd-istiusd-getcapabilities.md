---
UID: NF:stiusd.IStiUSD.GetCapabilities
title: IStiUSD::GetCapabilities (stiusd.h)
description: A still image minidriver's IStiUSD::GetCapabilities method returns a still image device's capabilities.
old-location: image\istiusd_getcapabilities.htm
tech.root: image
ms.assetid: baec1e38-360e-4f4f-82bd-bc89e3f8483d
ms.date: 05/03/2018
ms.keywords: GetCapabilities, GetCapabilities method [Imaging Devices], GetCapabilities method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],GetCapabilities method, IStiUSD.GetCapabilities, IStiUSD::GetCapabilities, image.istiusd_getcapabilities, stifnc_e0343c50-7695-417f-9742-1acd66f2791f.xml, stiusd/IStiUSD::GetCapabilities
ms.topic: method
f1_keywords:
 - "stiusd/IStiUSD.GetCapabilities"
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
- IStiUSD.GetCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::GetCapabilities


## -description


A still image minidriver's <b>IStiUSD::GetCapabilities</b> method returns a still image device's capabilities.


## -parameters




### -param pDevCaps






#### - pUsdCaps

Caller-supplied pointer to an empty <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/ns-stiusd-_sti_usd_caps">STI_USD_CAPS</a> structure.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiUSD::GetCapabilities</b> method should set appropriate device capability flags in the caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/ns-stiusd-_sti_usd_caps">STI_USD_CAPS</a> structure. It should also set the version number to STI_VERSION.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-getcapabilities">IStiDevice::GetCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStiUSD</a>
 

 

