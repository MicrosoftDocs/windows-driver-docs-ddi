---
UID: NE:dot11wdi._WDI_OPERATION_MODE
title: "_WDI_OPERATION_MODE"
author: windows-driver-content
description: The WDI_OPERATION_MODE enumeration defines operation modes.
old-location: netvista\wdi_operation_mode.htm
old-project: netvista
ms.assetid: 9838eeb9-6bd6-46a5-9361-6af3aa2d3014
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: dot11wdi/WDI_OPERATION_MODE_P2P_CLIENT, WDI_OPERATION_MODE_STA, WDI_OPERATION_MODE_P2P_DEVICE, dot11wdi/WDI_OPERATION_MODE, WDI_OPERATION_MODE_P2P_CLIENT, WDI_OPERATION_MODE_P2P_GO, dot11wdi/WDI_OPERATION_MODE_P2P_DEVICE, dot11wdi/WDI_OPERATION_MODE_STA, WDI_OPERATION_MODE enumeration [Network Drivers Starting with Windows Vista], netvista.wifi_operation_mode, _WDI_OPERATION_MODE, netvista.wdi_operation_mode, dot11wdi/WDI_OPERATION_MODE_P2P_GO, WDI_OPERATION_MODE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_OPERATION_MODE
product: Windows
targetos: Windows
req.typenames: WDI_OPERATION_MODE
---

# _WDI_OPERATION_MODE enumeration


## -description


The WDI_OPERATION_MODE enumeration defines operation modes.


## -syntax


````
typedef enum _WDI_OPERATION_MODE { 
  WDI_OPERATION_MODE_STA         = 0x1,
  WDI_OPERATION_MODE_P2P_DEVICE  = 0x8,
  WDI_OPERATION_MODE_P2P_CLIENT  = 0x10,
  WDI_OPERATION_MODE_P2P_GO      = 0x20
} WDI_OPERATION_MODE;
````


## -enum-fields




### -field WDI_OPERATION_MODE_STA

Infrastructure client.


### -field WDI_OPERATION_MODE_P2P_DEVICE

Wi-Fi Direct Device.


### -field WDI_OPERATION_MODE_P2P_CLIENT

Wi-Fi Direct Client.


### -field WDI_OPERATION_MODE_P2P_GO

Wi-Fi Direct Group Owner.

