---
UID: NS:d3dkmthk._D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
title: _D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
author: windows-driver-content
description: Used to get process device removal support.
ms.assetid: 28258371-4419-4aa9-aadb-e5e085fa503f
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT, D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT,
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	_D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT structure

## -description

Used to get process device removal support.

## -struct-fields

### -field hProcess

Handle to the process.

### -field AdapterLuid

Luid of Adapter that is potentially being detached.

### -field Support

Determines whether or not the process using the adapter can recover from graphics device removal.
