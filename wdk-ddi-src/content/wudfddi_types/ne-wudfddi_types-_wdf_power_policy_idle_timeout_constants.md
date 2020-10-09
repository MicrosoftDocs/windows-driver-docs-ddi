---
UID: NE:wudfddi_types._WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
title: _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS (wudfddi_types.h)
description: WDF_CALLBACK_CONSTRAINT enumeration
old-location: wdf\wdf_callback_constraint.htm
tech.root: wdf
ms.assetid: 118a9dcc-8dd4-454a-bab2-1558821781a7
ms.date: 02/26/2018
keywords: ["WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration"]
ms.keywords: None, WDF_CALLBACK_CONSTRAINT, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration, WdfDeviceLevel, WdfLevelReserved, _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, wdf.wdf_callback_constraint, wudfddi_types/None, wudfddi_types/WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, wudfddi_types/WdfDeviceLevel, wudfddi_types/WdfLevelReserved
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
req.typenames: WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
f1_keywords:
 - _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
 - wudfddi_types/_WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
 - WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
 - wudfddi_types/WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wudfddi_types.h
api_name:
 - WDF_CALLBACK_CONSTRAINT
---

# _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration (wudfddi_types.h)


## -description

## -enum-fields

### -field IdleTimeoutDefaultConstant

#### - None

No callback functions into the driver are synchronized.  The driver must handle all synchronization.


#### - WdfDeviceLevel

All callback functions into the driver that are associated with the device are synchronized, including all callback functions that are associated with I/O queues. Only one event handler that is associated with the device can run at any given time.


#### - WdfLevelReserved

Reserved.

## -remarks

Note that the above locking models apply only for I/O (that is, open, read, write, and device I/O control) operations and not for Plug and Play (PnP) and power management notifications.

