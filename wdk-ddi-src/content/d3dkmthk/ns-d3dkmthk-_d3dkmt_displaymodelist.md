---
UID: NS:d3dkmthk._D3DKMT_DISPLAYMODELIST
title: _D3DKMT_DISPLAYMODELIST (d3dkmthk.h)
description: Describes a list of display modes.
old-location: display\d3dkmt_displaymodelist.htm
ms.assetid: 2eb99f42-3639-4327-a880-47e18d1da71d
ms.date: 05/10/2018
ms.keywords: D3DKMT_DISPLAYMODELIST, D3DKMT_DISPLAYMODELIST structure [Display Devices], _D3DKMT_DISPLAYMODELIST, d3dkmthk/D3DKMT_DISPLAYMODELIST, display.d3dkmt_displaymodelist
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_DISPLAYMODELIST"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dkmthk.h
api_name:
- D3DKMT_DISPLAYMODELIST
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DISPLAYMODELIST
---

# _D3DKMT_DISPLAYMODELIST structure


## -description


Describes a list of display modes.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display modes apply to.


### -field ModeCount

[in/out] The number of display modes in the array that <b>pModeList</b> specifies.


### -field pModeList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_displaymode">D3DKMT_DISPLAYMODE</a> structures that represent the list of display modes.

