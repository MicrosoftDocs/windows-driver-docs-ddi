---
UID: NE:bthxddi._BTHX_SCO_SUPPORT
title: "_BTHX_SCO_SUPPORT"
author: windows-driver-content
description: The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.
old-location: bltooth\bthx_sco_support.htm
old-project: bltooth
ms.assetid: A9B303C7-868D-47EB-8279-9F655F58630C
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: ScoSupportNone, BTHX_SCO_SUPPORT, _BTHX_SCO_SUPPORT, ScoSupportHCI, BTHX_SCO_SUPPORT enumeration [Bluetooth Devices], bltooth.bthx_sco_support, bthxddi/BTHX_SCO_SUPPORT, bthxddi/ScoSupportHCIBypass, *PBTHX_SCO_SUPPORT, bthxddi/ScoSupportNone, ScoSupportHCIBypass, bthxddi/ScoSupportHCI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	BthXDDI.h
apiname:
-	BTHX_SCO_SUPPORT
product: Windows
targetos: Windows
req.typenames: BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT
---

# _BTHX_SCO_SUPPORT enumeration


## -description


The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.


## -syntax


````
typedef enum _BTHX_SCO_SUPPORT { 
  ScoSupportNone       = 0,
  ScoSupportHCI        = 1,
  ScoSupportHCIBypass  = 2
} BTHX_SCO_SUPPORT;
````


## -enum-fields




### -field ScoSupportNone

SCO is not supported.


### -field ScoSupportHCI

SCO data passes through the HCI layer (stack).


### -field ScoSupportHCIBypass

SCO data does not pass through the HCI layer but through a sideband mechanism like an I2S channel.


## -remarks


Upon starting, the Bluetooth stack will query the transport driver for its capabilities by sending the <a href="..\bthxddi\ni-bthxddi-ioctl_bthx_query_capabilities.md">IOCTL_BTHX_QUERY_CAPABILITIES</a> IOCTL.

The output buffer of this IOCTL is defined by the <a href="..\bthxddi\ns-bthxddi-_bthx_capabilities.md">BTHX_CAPABILITIES</a> structure which contains the 
BTHX_SCO_SUPPORT structure.

The transport driver must specify <b>ScoSupportHCIBypass</b>.


