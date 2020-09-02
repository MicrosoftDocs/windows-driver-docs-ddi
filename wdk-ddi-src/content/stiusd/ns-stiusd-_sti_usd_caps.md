---
UID: NS:stiusd._STI_USD_CAPS
title: _STI_USD_CAPS (stiusd.h)
description: The STI_USD_CAPS structure is used as a parameter for the IStiUSD::GetCapabilities method.
old-location: image\sti_usd_caps.htm
tech.root: image
ms.assetid: 24dda069-5f93-469d-8ce3-87b488019b88
ms.date: 05/03/2018
keywords: ["STI_USD_CAPS structure"]
ms.keywords: "*PSTI_USD_CAPS, PSTI_USD_CAPS, PSTI_USD_CAPS structure pointer [Imaging Devices], STI_USD_CAPS, STI_USD_CAPS structure [Imaging Devices], _STI_USD_CAPS, image.sti_usd_caps, stifnc_4f136561-e3a7-467d-b8be-a60db8534126.xml, stiusd/PSTI_USD_CAPS, stiusd/STI_USD_CAPS"
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Windows
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
targetos: Windows
req.typenames: STI_USD_CAPS, *PSTI_USD_CAPS
f1_keywords:
 - _STI_USD_CAPS
 - stiusd/_STI_USD_CAPS
 - PSTI_USD_CAPS
 - stiusd/PSTI_USD_CAPS
 - STI_USD_CAPS
 - stiusd/STI_USD_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - stiusd.h
api_name:
 - STI_USD_CAPS
---

# _STI_USD_CAPS structure


## -description

The STI_USD_CAPS structure is used as a parameter for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getcapabilities">IStiUSD::GetCapabilities</a> method.

## -struct-fields

### -field dwVersion

STI version number. This value must be STI_VERSION, defined in <i>Sti.h</i>.

### -field dwGenericCaps

Bit flags indicating driver capabilities. The following flags are defined in <i>Stiusd.h</i>.





#### STI_USD_GENCAP_NATIVE_PUSHSUPPORT

The driver supports asynchronous device notifications.





#### STI_USD_GENCAP_OPEN_DEVICE_FOR_ME

<i>Not used.</i>

