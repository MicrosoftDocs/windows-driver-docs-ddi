---
UID: NE:dot11wdi._WDI_RX_INDICATION_LEVEL
title: "_WDI_RX_INDICATION_LEVEL"
author: windows-driver-content
description: The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.
old-location: netvista\wdi_rx_indication_level.htm
old-project: netvista
ms.assetid: 73ad8d04-c245-4a3c-92ff-4729737ede92
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC, _WDI_RX_INDICATION_LEVEL, WDI_RX_INDICATION_PASSIVE, WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES, WDI_RX_INDICATION_LEVEL enumeration [Network Drivers Starting with Windows Vista], dot11wdi/WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES, dot11wdi/WDI_RX_INDICATION_PASSIVE, dot11wdi/WDI_RX_INDICATION_LEVEL, WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES, dot11wdi/WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES, dot11wdi/WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC, WDI_RX_INDICATION_FLAG_RESOURCES, dot11wdi/WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES, netvista.wdi_rx_indication_level, dot11wdi/WDI_RX_INDICATION_DISPATCH_GENERAL, netvista.wifi_rx_indication_level, WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES, dot11wdi/WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES, WDI_RX_INDICATION_LEVEL, WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES, WDI_RX_INDICATION_DISPATCH_GENERAL, dot11wdi/WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES, WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES, dot11wdi/WDI_RX_INDICATION_FLAG_RESOURCES
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
-	WDI_RX_INDICATION_LEVEL
product: Windows
targetos: Windows
req.typenames: WDI_RX_INDICATION_LEVEL
---

# _WDI_RX_INDICATION_LEVEL enumeration


## -description


The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.


## -syntax


````
typedef enum _WDI_RX_INDICATION_LEVEL { 
  WDI_RX_INDICATION_DISPATCH_GENERAL                           = 0,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC                      = 1,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES                      = 2,
  WDI_RX_INDICATION_PASSIVE                                    = 3,
  WDI_RX_INDICATION_FLAG_RESOURCES                             = 0x80000000,
  WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES        = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_GENERAL,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES  = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES   = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES,
  WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES                 = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_PASSIVE
} WDI_RX_INDICATION_LEVEL;
````


## -enum-fields




### -field WDI_RX_INDICATION_DISPATCH_GENERAL

Used for subsequent data indications in a DPC. <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b> is used for the first data indication of a DPC.


### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC

Used for the first data indication (<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_inorder_data_ind.md">NdisWdiRxInorderDataIndication</a>) of a DPC.


### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES

Used when making data indications in the context of <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a>.


### -field WDI_RX_INDICATION_PASSIVE

Used when making data indications at passive level.


### -field WDI_RX_INDICATION_FLAG_RESOURCES

Bitwise OR’d with other enum values to cause RxMgr to set <b>NDIS_RECEIVE_FLAG_RESOURCES</b>.


### -field WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_GENERAL</b>.


### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b>.


### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES</b>.


### -field WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_PASSIVE</b>.

