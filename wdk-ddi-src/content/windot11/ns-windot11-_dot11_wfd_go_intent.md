---
UID: NS:windot11._DOT11_WFD_GO_INTENT
title: "_DOT11_WFD_GO_INTENT"
author: windows-driver-content
description: The DOT11_WFD_GO_INTENT structure represents the Group Intent value used during Group Owner Negotiation
old-location: netvista\_dot11_wfd_go_intent.htm
old-project: netvista
ms.assetid: 8E4F88EF-04A9-4313-AE6A-2467DA08044A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_WFD_GO_INTENT, PDOT11_WFD_GO_INTENT structure pointer [Network Drivers Starting with Windows Vista], netvista._dot11_wfd_go_intent, windot11/PDOT11_WFD_GO_INTENT, windot11/DOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT structure [Network Drivers Starting with Windows Vista], _DOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT, PDOT11_WFD_GO_INTENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
-	Windot11.h
apiname:
-	DOT11_WFD_GO_INTENT
product: Windows
targetos: Windows
req.typenames: DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT
req.product: Windows 10 or later.
---

# _DOT11_WFD_GO_INTENT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_GO_INTENT</b> structure represents the Group Intent value used during Group Owner Negotiation


## -syntax


````
typedef struct _DOT11_WFD_GO_INTENT {
  UCHAR TieBreaker:1;
  UCHAR Intent:7;
} DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT;
````


## -struct-fields




### -field TieBreaker

 


### -field Intent

 




#### - Intent:7

Group ownership intent level. The value of the local device intent is compared to the remote device intent to negociate ownership.


#### - TieBreaker:1

If set, indicates that group ownership is granted.

