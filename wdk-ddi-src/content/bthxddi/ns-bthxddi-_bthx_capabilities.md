---
UID: NS:bthxddi._BTHX_CAPABILITIES
title: "_BTHX_CAPABILITIES"
author: windows-driver-content
description: The BTHX_CAPABILITIES structure describes the capabilities of the Bluetooth Extensible Transport Driver.
old-location: bltooth\bthx_capabilities.htm
old-project: bltooth
ms.assetid: BEC06C82-E103-4255-ACDD-9FB28E8E2DE5
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PBTHX_CAPABILITIES, BTHX_CAPABILITIES, BTHX_CAPABILITIES structure [Bluetooth Devices], PBTHX_CAPABILITIES, PBTHX_CAPABILITIES structure pointer [Bluetooth Devices], _BTHX_CAPABILITIES, bltooth.bthx_capabilities, bthxddi/BTHX_CAPABILITIES, bthxddi/PBTHX_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	BthXDDI.h
api_name:
-	BTHX_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: BTHX_CAPABILITIES, *PBTHX_CAPABILITIES
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

