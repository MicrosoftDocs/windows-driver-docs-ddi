---
UID: NS:wlanihv._DOT11_EAP_RESULT
title: _DOT11_EAP_RESULT (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_eap_result.htm
tech.root: netvista
ms.assetid: 90898f5c-ffc1-4e6c-a8f8-ba839f449082
ms.date: 02/16/2018
keywords: ["_DOT11_EAP_RESULT structure"]
ms.keywords: "*PDOT11_EAP_RESULT, DOT11_EAP_RESULT, DOT11_EAP_RESULT structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_85e62087-2509-442a-b513-ae48577e0b77.xml, PDOT11_EAP_RESULT, PDOT11_EAP_RESULT structure pointer [Network Drivers Starting with Windows Vista], _DOT11_EAP_RESULT, netvista.dot11_eap_result, wlanihv/DOT11_EAP_RESULT, wlanihv/PDOT11_EAP_RESULT"
f1_keywords:
 - "wlanihv/DOT11_EAP_RESULT"
req.header: wlanihv.h
req.include-header: Winlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- HeaderDef
api_location:
- wlanihv.h
api_name:
- DOT11_EAP_RESULT
product:
- Windows
targetos: Windows
req.typenames: DOT11_EAP_RESULT, *PDOT11_EAP_RESULT
req.product: Windows 10 or later.
---

# _DOT11_EAP_RESULT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_EAP_RESULT structure indicates results from an EAP method.


## -syntax


```cpp
typedef struct _DOT11_EAP_RESULT {
  UINT32         dwFailureReasonCode;
  EAP_ATTRIBUTES *pAttribArray;
} DOT11_EAP_RESULT, *PDOT11_EAP_RESULT;
```


## -struct-fields




### -field dwFailureReasonCode

The reason code returned by the EAP method. The meaning of the code is specific to the EAP
     method.


### -field pAttribArray

A pointer to an EAP_ATTRIBUTES array structure that contains the EAP attributes returned by the
     authentication session. For more information about EAP_ATTRIBUTES, see the Microsoft Windows SDK
     documentation.

