---
UID: NS:windot11._DOT11_WFD_CONFIGURATION_TIMEOUT
title: "_DOT11_WFD_CONFIGURATION_TIMEOUT"
author: windows-driver-content
description: The DOT11_WFD_CONFIGURATION_TIMEOUT structure contains configuration time-out parameters.
old-location: netvista\dot11_wfd_configuration_timeout.htm
old-project: netvista
ms.assetid: 5432EB69-933A-4080-919F-4131DC4044D0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_WFD_CONFIGURATION_TIMEOUT, ,, 1, A, C, D, DOT11_WFD_CONFIGURATION_TIMEOUT, DOT11_WFD_CONFIGURATION_TIMEOUT structure [Network Drivers Starting with Windows Vista], E, F, G, I, M, N, O, P, PDOT11_WFD_CONFIGURATION_TIMEOUT, PDOT11_WFD_CONFIGURATION_TIMEOUT structure pointer [Network Drivers Starting with Windows Vista], R, T, U, W, _, _DOT11_WFD_CONFIGURATION_TIMEOUT, netvista.dot11_wfd_configuration_timeout, windot11/DOT11_WFD_CONFIGURATION_TIMEOUT, windot11/PDOT11_WFD_CONFIGURATION_TIMEOUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	DOT11_WFD_CONFIGURATION_TIMEOUT
product: Windows
targetos: Windows
req.typenames: DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT
req.product: Windows 10 or later.
---

# _DOT11_WFD_CONFIGURATION_TIMEOUT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_CONFIGURATION_TIMEOUT</b> structure contains configuration time-out parameters.


## -syntax


````
typedef struct _DOT11_WFD_CONFIGURATION_TIMEOUT {
  UCHAR GOTimeout;
  UCHAR ClientTimeout;
} DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT;
````


## -struct-fields




### -field GOTimeout

The time, in milliseconds, allowed to configure as a Group Owner (GO). The miniport must convert this value to the correct units before including it in a Peer-to-Peer Information Element (P2P IE).


### -field ClientTimeout

The time, in milliseconds, allowed to configure as a client. The miniport must convert this value to the correct units before including it in a P2P IE.

