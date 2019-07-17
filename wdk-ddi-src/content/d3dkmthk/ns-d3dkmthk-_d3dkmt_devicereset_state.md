---
UID: NS:d3dkmthk._D3DKMT_DEVICERESET_STATE
title: _D3DKMT_DEVICERESET_STATE (d3dkmthk.h)
description: The D3DKMT_DEVICERESET_STATE structure identifies reset status.
old-location: display\d3dkmt_devicereset_state.htm
ms.assetid: c2037d77-8745-4307-ac12-54f62f20c2d9
ms.date: 05/10/2018
ms.keywords: D3DKMT_DEVICERESET_STATE, D3DKMT_DEVICERESET_STATE structure [Display Devices], OpenGL_Structs_03e42382-c472-4f0b-9183-a1b6630f64cf.xml, _D3DKMT_DEVICERESET_STATE, d3dkmthk/D3DKMT_DEVICERESET_STATE, display.d3dkmt_devicereset_state
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_DEVICERESET_STATE"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmthk.h
api_name:
- D3DKMT_DEVICERESET_STATE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DEVICERESET_STATE
---

# _D3DKMT_DEVICERESET_STATE structure


## -description


The D3DKMT_DEVICERESET_STATE structure identifies reset status.


## -struct-fields




### -field DesktopSwitched

A UINT value that specifies whether the desktop that the calling process is created on switched from being visible to being invisible. For example, when the security screen appears because a user pressed CTRL+ALT+DEL, the desktop that the calling process is created on becomes invisible. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A 32-bit value that identifies reset status.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getdevicestate">D3DKMT_GETDEVICESTATE</a>
 

 

