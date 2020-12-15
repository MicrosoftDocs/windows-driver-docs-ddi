---
UID: NS:bthxddi._BTHX_CAPABILITIES
title: _BTHX_CAPABILITIES (bthxddi.h)
description: The BTHX_CAPABILITIES structure describes the capabilities of the Bluetooth Extensible Transport Driver.
old-location: bltooth\bthx_capabilities.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["BTHX_CAPABILITIES structure"]
ms.keywords: "*PBTHX_CAPABILITIES, BTHX_CAPABILITIES, BTHX_CAPABILITIES structure [Bluetooth Devices], PBTHX_CAPABILITIES, PBTHX_CAPABILITIES structure pointer [Bluetooth Devices], _BTHX_CAPABILITIES, bltooth.bthx_capabilities, bthxddi/BTHX_CAPABILITIES, bthxddi/PBTHX_CAPABILITIES"
req.header: bthxddi.h
req.include-header: BthXDDI.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported starting with  Windows 8.
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
targetos: Windows
req.typenames: BTHX_CAPABILITIES, *PBTHX_CAPABILITIES
f1_keywords:
 - _BTHX_CAPABILITIES
 - bthxddi/_BTHX_CAPABILITIES
 - PBTHX_CAPABILITIES
 - bthxddi/PBTHX_CAPABILITIES
 - BTHX_CAPABILITIES
 - bthxddi/BTHX_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthXDDI.h
api_name:
 - BTHX_CAPABILITIES
---

# _BTHX_CAPABILITIES structure


## -description

The BTHX_CAPABILITIES structure describes the capabilities of the Bluetooth Extensible Transport Driver.

## -struct-fields

### -field MaxAclTransferInSize

The maximum size, in bytes, of the ACL packets the transport layer can accept.

### -field ScoSupport

The type of SCO supported. This must be set to <b>ScoSupportHCIBypass</b>.

### -field MaxScoChannels

The maximum supported number of SCO channels. This must be set to 1.

### -field IsDeviceIdleCapable

Whether the device supports idle/sleep power state. TRUE if the device can support idle (in low duty cycle state), else FALSE.

### -field IsDeviceWakeCapable

Whether the device supports remote wake. TRUE if the device supports waking the system from sleep, else FALSE.

