---
UID: NE:wditypes._WDI_CAN_SUSTAIN_AP_REASON
title: _WDI_CAN_SUSTAIN_AP_REASON (wditypes.h)
description: The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a OID_WDI_TASK_START_AP request.
old-location: netvista\wdi_can_sustain_ap_reason.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_CAN_SUSTAIN_AP_REASON enumeration"]
ms.keywords: WDI_CAN_SUSTAIN_AP_REASON, WDI_CAN_SUSTAIN_AP_REASON enumeration [Network Drivers Starting with Windows Vista], WDI_CAN_SUSTAIN_AP_REASON_IHV_END, WDI_CAN_SUSTAIN_AP_REASON_IHV_START, _WDI_CAN_SUSTAIN_AP_REASON, netvista.wdi_can_sustain_ap_reason, wditypes/WDI_CAN_SUSTAIN_AP_REASON, wditypes/WDI_CAN_SUSTAIN_AP_REASON_IHV_END, wditypes/WDI_CAN_SUSTAIN_AP_REASON_IHV_START
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
targetos: Windows
req.typenames: WDI_CAN_SUSTAIN_AP_REASON
f1_keywords:
 - _WDI_CAN_SUSTAIN_AP_REASON
 - wditypes/_WDI_CAN_SUSTAIN_AP_REASON
 - WDI_CAN_SUSTAIN_AP_REASON
 - wditypes/WDI_CAN_SUSTAIN_AP_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_CAN_SUSTAIN_AP_REASON
 - WDI_CAN_SUSTAIN_AP_REASON
---

# _WDI_CAN_SUSTAIN_AP_REASON enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a <a href="/windows-hardware/drivers/network/oid-wdi-task-start-ap">OID_WDI_TASK_START_AP</a> request.

## -enum-fields

### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.

