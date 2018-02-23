---
UID: NS:wlanihv._DOT11_EAP_RESULT
title: "_DOT11_EAP_RESULT"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_eap_result.htm
old-project: netvista
ms.assetid: 90898f5c-ffc1-4e6c-a8f8-ba839f449082
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11_EAP_RESULT, wlanihv/PDOT11_EAP_RESULT, wlanihv/DOT11_EAP_RESULT, *PDOT11_EAP_RESULT, PDOT11_EAP_RESULT structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_eap_result, _DOT11_EAP_RESULT, DOT11_EAP_RESULT structure [Network Drivers Starting with Windows Vista], PDOT11_EAP_RESULT, Native_802.11_data_types_85e62087-2509-442a-b513-ae48577e0b77.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlanihv.h
apiname:
-	DOT11_EAP_RESULT
product: Windows
targetos: Windows
req.typenames: DOT11_EAP_RESULT, *PDOT11_EAP_RESULT
req.product: Windows 10 or later.
---

# _DOT11_EAP_RESULT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_EAP_RESULT structure indicates results from an EAP method.


## -syntax


````
typedef struct _DOT11_EAP_RESULT {
  UINT32         dwFailureReasonCode;
  EAP_ATTRIBUTES *pAttribArray;
} DOT11_EAP_RESULT, *PDOT11_EAP_RESULT;
````


## -struct-fields




### -field dwFailureReasonCode

The reason code returned by the EAP method. The meaning of the code is specific to the EAP
     method.


### -field pAttribArray

A pointer to an EAP_ATTRIBUTES array structure that contains the EAP attributes returned by the
     authentication session. For more information about EAP_ATTRIBUTES, see the Microsoft Windows SDK
     documentation.

