---
UID: NE:wditypes._WDI_POWER_MODE_REASON_CODE
title: _WDI_POWER_MODE_REASON_CODE (wditypes.h)
description: The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.
old-location: netvista\wdi_power_mode_reason_code.htm
tech.root: netvista
ms.assetid: F9FAA622-A844-4D9F-A0E6-D919C1FAD3AB
ms.date: 05/02/2018
ms.keywords: WDI_POWER_MODE_REASON_CODE, WDI_POWER_MODE_REASON_CODE enumeration [Network Drivers Starting with Windows Vista], WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP, WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE, WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE, WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP, WDI_POWER_MODE_REASON_CODE_NO_CHANGE, WDI_POWER_MODE_REASON_CODE_OTHERS, _WDI_POWER_MODE_REASON_CODE, netvista.wdi_power_mode_reason_code, netvista.wifi_power_mode_reason_code, wditypes/WDI_POWER_MODE_REASON_CODE, wditypes/WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP, wditypes/WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE, wditypes/WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE, wditypes/WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP, wditypes/WDI_POWER_MODE_REASON_CODE_NO_CHANGE, wditypes/WDI_POWER_MODE_REASON_CODE_OTHERS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_POWER_MODE_REASON_CODE
product:
- Windows
targetos: Windows
req.typenames: WDI_POWER_MODE_REASON_CODE
---

# _WDI_POWER_MODE_REASON_CODE enumeration


## -description


The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.


## -enum-fields




### -field WDI_POWER_MODE_REASON_CODE_NO_CHANGE

Device is initially in this state and has not changed since.


### -field WDI_POWER_MODE_REASON_CODE_NONCOMPLANT_AP


### -field WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE

WFD device is legacy.


### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP

AP is compliant.


### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE

All connected WFD device can do PSM.


### -field WDI_POWER_MODE_REASON_CODE_OTHERS

Other reason.


#### - WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP

AP is not compliant. As to be in CAM.

