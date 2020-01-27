---
UID: NS:d3dkmthk._D3DKMT_SETVIDPNSOURCEHWPROTECTION
title: _D3DKMT_SETVIDPNSOURCEHWPROTECTION (d3dkmthk.h)
description: Used to set VidPn source hardware protection.
ms.assetid: 692b580b-0e46-4840-aae8-78450d71aaaf
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/_D3DKMT_SETVIDPNSOURCEHWPROTECTION"
ms.keywords: _D3DKMT_SETVIDPNSOURCEHWPROTECTION, D3DKMT_SETVIDPNSOURCEHWPROTECTION, 
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
req.typenames: D3DKMT_SETVIDPNSOURCEHWPROTECTION
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_SETVIDPNSOURCEHWPROTECTION
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_SETVIDPNSOURCEHWPROTECTION structure

## -description

Used to set VidPn source hardware protection.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field HwProtected
 
Indicates whether the VidPn source is hardware protected.

## -remarks

## -see-also
