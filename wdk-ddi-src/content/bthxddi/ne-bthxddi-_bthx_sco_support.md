---
UID: NE:bthxddi._BTHX_SCO_SUPPORT
title: _BTHX_SCO_SUPPORT (bthxddi.h)
description: The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.
old-location: bltooth\bthx_sco_support.htm
tech.root: bltooth
ms.assetid: A9B303C7-868D-47EB-8279-9F655F58630C
ms.date: 04/27/2018
ms.keywords: "*PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT enumeration [Bluetooth Devices], ScoSupportHCI, ScoSupportHCIBypass, ScoSupportNone, _BTHX_SCO_SUPPORT, bltooth.bthx_sco_support, bthxddi/BTHX_SCO_SUPPORT, bthxddi/ScoSupportHCI, bthxddi/ScoSupportHCIBypass, bthxddi/ScoSupportNone"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- BthXDDI.h
api_name:
- BTHX_SCO_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT
---

# _BTHX_SCO_SUPPORT enumeration


## -description


The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.


## -enum-fields




### -field ScoSupportNone

SCO is not supported.


### -field ScoSupportHCI

SCO data passes through the HCI layer (stack).


### -field ScoSupportHCIBypass

SCO data does not pass through the HCI layer but through a sideband mechanism like an I2S channel.


## -remarks



Upon starting, the Bluetooth stack will query the transport driver for its capabilities by sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthxddi/ni-bthxddi-ioctl_bthx_query_capabilities">IOCTL_BTHX_QUERY_CAPABILITIES</a> IOCTL.

The output buffer of this IOCTL is defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthxddi/ns-bthxddi-_bthx_capabilities">BTHX_CAPABILITIES</a> structure which contains the 
BTHX_SCO_SUPPORT structure.

The transport driver must specify <b>ScoSupportHCIBypass</b>.



