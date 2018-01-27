---
UID: NE:wditypes._WDI_ROAM_TRIGGER
title: _WDI_ROAM_TRIGGER
author: windows-driver-content
description: The WDI_ROAM_TRIGGER enumeration defines roam triggers.
old-location: netvista\wdi_roam_trigger.htm
old-project: netvista
ms.assetid: 7AFA084B-5EFC-429B-B6D1-F4E484B16921
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wditypes/WDI_ROAM_TRIGGER_OTHER, WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST, wditypes/WDI_ROAM_TRIGGER, netvista.wdi_roam_trigger, WDI_ROAM_TRIGGER, WDI_ROAM_TRIGGER enumeration [Network Drivers Starting with Windows Vista], WDI_ROAM_TRIGGER_OTHER, _WDI_ROAM_TRIGGER, wditypes/WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST
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
-	WDI_ROAM_TRIGGER
product: Windows
targetos: Windows
req.typenames: WDI_ROAM_TRIGGER
req.product: Windows 10 or later.
---

# _WDI_ROAM_TRIGGER enumeration


## -description


The WDI_ROAM_TRIGGER enumeration defines roam triggers.


## -syntax


````
typedef enum _WDI_ROAM_TRIGGER { 
  WDI_ROAM_TRIGGER_OTHER                            = 0x00000000,
  WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST  = 0x00000001
} WDI_ROAM_TRIGGER;
````


## -enum-fields




### -field WDI_ROAM_TRIGGER_OTHER

None.


### -field WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST

This value is for roams due to a BSS Transition Request by the AP with the Disassociation Imminent bit set.

