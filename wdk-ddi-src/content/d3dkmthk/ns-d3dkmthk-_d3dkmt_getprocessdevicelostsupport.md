---
UID: NS:d3dkmthk._D3DKMT_GETPROCESSDEVICELOSTSUPPORT
title: D3DKMT_GETPROCESSDEVICELOSTSUPPORT (d3dkmthk.h)
description: Used to get the indicated process.
old-location: display\d3dkmt-getprocessdevicelostsupport.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure"]
ms.keywords: D3DKMT_GETPROCESSDEVICELOSTSUPPORT, D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure [Display Devices], _D3DKMT_GETPROCESSDEVICELOSTSUPPORT, d3dkmthk/D3DKMT_GETPROCESSDEVICELOSTSUPPORT, display.d3dkmt-getprocessdevicelostsupport
f1_keywords:
 - "d3dkmthk/D3DKMT_GETPROCESSDEVICELOSTSUPPORT"
 - "D3DKMT_GETPROCESSDEVICELOSTSUPPORT"
req.header: d3dkmthk.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- d3dkmthk.h
api_name:
- D3DKMT_GETPROCESSDEVICELOSTSUPPORT
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETPROCESSDEVICELOSTSUPPORT
---

# D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure

## -description

Used to get the indicated process.

## -struct-fields

### -field hProcess

A handle to the process.

### -field AdapterLuid

LUID of Adapter that is potentially being detached

### -field Support

Indicates whether or not all devices of the process using the adapter can recover from graphics device lost.
