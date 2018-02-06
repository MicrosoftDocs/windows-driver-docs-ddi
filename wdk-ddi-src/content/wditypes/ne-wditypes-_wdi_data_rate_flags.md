---
UID: NE:wditypes._WDI_DATA_RATE_FLAGS
title: "_WDI_DATA_RATE_FLAGS"
author: windows-driver-content
description: The WDI_DATA_RATE_FLAGS enumeration defines the data rate flags.
old-location: netvista\wdi_data_rate_flags.htm
old-project: netvista
ms.assetid: 937D1C48-AC5A-4D55-8722-BDC1192613A9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wifi_data_rate_flags, wditypes/WDI_DATA_RATE_TX_RATE, _WDI_DATA_RATE_FLAGS, WDI_DATA_RATE_FLAGS, wditypes/WDI_DATA_RATE_RX_RATE, netvista.wdi_data_rate_flags, WDI_DATA_RATE_NON_STANDARD, WDI_DATA_RATE_FLAGS enumeration [Device and Driver Installation], WDI_DATA_RATE_RX_RATE, WDI_DATA_RATE_TX_RATE, wditypes/WDI_DATA_RATE_FLAGS, wditypes/WDI_DATA_RATE_NON_STANDARD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname:
-	WDI_DATA_RATE_FLAGS
product: Windows
targetos: Windows
req.typenames: WDI_DATA_RATE_FLAGS
req.product: Windows 10 or later.
---

# _WDI_DATA_RATE_FLAGS enumeration


## -description


The WDI_DATA_RATE_FLAGS enumeration defines the data rate flags.


## -syntax


````
typedef enum _WDI_DATA_RATE_FLAGS { 
  WDI_DATA_RATE_NON_STANDARD  = 0x01,
  WDI_DATA_RATE_RX_RATE       = 0x02,
  WDI_DATA_RATE_TX_RATE       = 0x04
} WDI_DATA_RATE_FLAGS;
````


## -enum-fields




### -field WDI_DATA_RATE_NON_STANDARD

The data rate is not a standard data rate defined in the IEEE 802.11 standards.


### -field WDI_DATA_RATE_RX_RATE

The data rate can be used for RX.


### -field WDI_DATA_RATE_TX_RATE

The data rate can be used for TX.

