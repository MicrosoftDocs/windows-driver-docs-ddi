---
UID: NS:d3dkmthk._D3DKMT_SETDEVICELOSTSUPPORT
title: _D3DKMT_SETDEVICELOSTSUPPORT (d3dkmthk.h)
description: Used to indicate whether a device can recover from losing a graphics device.
old-location: display\d3dkmt-setdevicelostsupport.htm
ms.assetid: 191ea8ac-6646-44db-88eb-54dc51afef17
ms.date: 05/10/2018
ms.keywords: D3DKMT_SETDEVICELOSTSUPPORT, D3DKMT_SETDEVICELOSTSUPPORT structure [Display Devices], _D3DKMT_SETDEVICELOSTSUPPORT, d3dkmthk/D3DKMT_SETDEVICELOSTSUPPORT, display.d3dkmt-setdevicelostsupport
ms.topic: struct
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
- D3DKMT_SETDEVICELOSTSUPPORT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETDEVICELOSTSUPPORT
---

# _D3DKMT_SETDEVICELOSTSUPPORT structure


## -description


Used to indicate whether a device can recover from losing a graphics device.


## -struct-fields




### -field hDevice

A handle to the device.


### -field Support

Indicates whether or not the device can recover from losing the graphics device.

