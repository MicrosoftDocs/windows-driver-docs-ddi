---
UID: NE:dot11wdi._WDI_FRAME_PAYLOAD_TYPE
title: "_WDI_FRAME_PAYLOAD_TYPE"
author: windows-driver-content
description: The WDI_FRAME_PAYLOAD_TYPE enumeration defines the frame payload type.
old-location: netvista\wdi_frame_payload_type.htm
old-project: netvista
ms.assetid: 28aef1bd-915a-4f05-a4b0-bec63ddfdfb5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WDI_FRAME_MSDU, WDI_FRAME_MSDU_FRAGMENT, WDI_FRAME_PAYLOAD_TYPE, WDI_FRAME_PAYLOAD_TYPE enumeration [Network Drivers Starting with Windows Vista], _WDI_FRAME_PAYLOAD_TYPE, dot11wdi/WDI_FRAME_MSDU, dot11wdi/WDI_FRAME_MSDU_FRAGMENT, dot11wdi/WDI_FRAME_PAYLOAD_TYPE, netvista.wdi_frame_payload_type, netvista.wifi_frame_payload_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	WDI_FRAME_PAYLOAD_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_FRAME_PAYLOAD_TYPE
---

# _WDI_FRAME_PAYLOAD_TYPE enumeration


## -description


The WDI_FRAME_PAYLOAD_TYPE enumeration defines the frame payload type.


## -syntax


````
typedef enum _WDI_FRAME_PAYLOAD_TYPE { 
  WDI_FRAME_MSDU           = 0,
  WDI_FRAME_MSDU_FRAGMENT  = 1
} WDI_FRAME_PAYLOAD_TYPE;
````


## -enum-fields




### -field WDI_FRAME_MSDU

MAC service data unit (MSDU).


### -field WDI_FRAME_MSDU_FRAGMENT

MAC service data unit (MSDU) fragment.

