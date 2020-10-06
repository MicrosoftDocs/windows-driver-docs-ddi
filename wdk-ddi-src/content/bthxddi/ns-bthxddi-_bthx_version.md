---
UID: NS:bthxddi._BTHX_VERSION
title: _BTHX_VERSION (bthxddi.h)
description: The BTHX_VERSION structure describes the version or versions that the transport driver supports.
old-location: bltooth\bthx_version.htm
tech.root: bltooth
ms.assetid: 2C5CC5B1-52F1-4DF5-9397-E8FD4983BA25
ms.date: 04/27/2018
keywords: ["BTHX_VERSION structure"]
ms.keywords: "*PBTHX_VERSION, BTHX_VERSION, BTHX_VERSION structure [Bluetooth Devices], _BTHX_VERSION, bltooth.bthx_version, bthxddi/_BTHX_VERSION"
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
req.typenames: BTHX_VERSION, *PBTHX_VERSION
f1_keywords:
 - _BTHX_VERSION
 - bthxddi/_BTHX_VERSION
 - PBTHX_VERSION
 - bthxddi/PBTHX_VERSION
 - BTHX_VERSION
 - bthxddi/BTHX_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthXDDI.h
api_name:
 - _BTHX_VERSION
---

# _BTHX_VERSION structure


## -description

The BTHX_VERSION structure describes the version or versions that the transport driver supports.

## -struct-fields

### -field Version

Bitmask of supported versions. Currently, BTHX_DDI_VERSION_1   is the only supported version.

