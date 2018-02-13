---
UID: NE:wditypes._WDI_CAN_SUSTAIN_AP_REASON
title: "_WDI_CAN_SUSTAIN_AP_REASON"
author: windows-driver-content
description: The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a OID_WDI_TASK_START_AP request.
old-location: netvista\wdi_can_sustain_ap_reason.htm
old-project: netvista
ms.assetid: 9AAE4B3F-7C5C-457D-9388-63E6E6AB8A2E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WDI_CAN_SUSTAIN_AP_REASON, WDI_CAN_SUSTAIN_AP_REASON_IHV_START, WDI_CAN_SUSTAIN_AP_REASON, wditypes/WDI_CAN_SUSTAIN_AP_REASON_IHV_START, netvista.wdi_can_sustain_ap_reason, wditypes/WDI_CAN_SUSTAIN_AP_REASON_IHV_END, WDI_CAN_SUSTAIN_AP_REASON enumeration [Network Drivers Starting with Windows Vista], wditypes/WDI_CAN_SUSTAIN_AP_REASON, WDI_CAN_SUSTAIN_AP_REASON_IHV_END"
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
-	WDI_CAN_SUSTAIN_AP_REASON
product: Windows
targetos: Windows
req.typenames: WDI_CAN_SUSTAIN_AP_REASON
req.product: Windows 10 or later.
---

# _WDI_CAN_SUSTAIN_AP_REASON enumeration


## -description


The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925964">OID_WDI_TASK_START_AP</a> request.


## -syntax


````
typedef enum _WDI_CAN_SUSTAIN_AP_REASON { 
  WDI_CAN_SUSTAIN_AP_REASON_IHV_START  = 0xFF000000,
  WDI_CAN_SUSTAIN_AP_REASON_IHV_END    = 0xFFFFFFFF
} WDI_CAN_SUSTAIN_AP_REASON;
````


## -enum-fields




### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.


### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.

