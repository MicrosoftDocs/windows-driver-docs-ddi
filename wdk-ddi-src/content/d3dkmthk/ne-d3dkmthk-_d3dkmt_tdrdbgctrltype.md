---
UID: NE:d3dkmthk._D3DKMT_TDRDBGCTRLTYPE
title: _D3DKMT_TDRDBGCTRLTYPE (d3dkmthk.h)
description: The D3DKMT_TDRDBGCTRLTYPE enumeration type contains values that affect the behavior of the operating system's Timeout Detection and Recovery (TDR) process in a call to the OpenGL D3DKMTEscape function.
old-location: display\d3dkmt_tdrdbgctrltype.htm
ms.assetid: d3a6dfcc-e318-4fd0-85e0-5a0cc13fd00f
ms.date: 05/10/2018
ms.keywords: D3DKMT_TDRDBGCTRLTYPE, D3DKMT_TDRDBGCTRLTYPE enumeration [Display Devices], D3DKMT_TDRDBGCTRLTYPE_DISABLEBREAK, D3DKMT_TDRDBGCTRLTYPE_ENABLEBREAK, D3DKMT_TDRDBGCTRLTYPE_ENGINETDR, D3DKMT_TDRDBGCTRLTYPE_FORCEDODTDR, D3DKMT_TDRDBGCTRLTYPE_FORCEDODVSYNCTDR, D3DKMT_TDRDBGCTRLTYPE_FORCETDR, D3DKMT_TDRDBGCTRLTYPE_GPUTDR, D3DKMT_TDRDBGCTRLTYPE_UNCONDITIONAL, D3DKMT_TDRDBGCTRLTYPE_VSYNCTDR, OpenGL_Structs_7c8128ed-aa43-4943-bc1f-948da6163316.xml, _D3DKMT_TDRDBGCTRLTYPE, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_DISABLEBREAK, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_ENABLEBREAK, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_ENGINETDR, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_FORCEDODTDR, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_FORCEDODVSYNCTDR, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_FORCETDR, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_GPUTDR, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_UNCONDITIONAL, d3dkmthk/D3DKMT_TDRDBGCTRLTYPE_VSYNCTDR, display.d3dkmt_tdrdbgctrltype
ms.topic: enum
f1_keywords:
 - "d3dkmthk/D3DKMT_TDRDBGCTRLTYPE"
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
- D3DKMT_TDRDBGCTRLTYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_TDRDBGCTRLTYPE
---

# _D3DKMT_TDRDBGCTRLTYPE enumeration


## -description


<b>Do not use the D3DKMT_TDRDBGCTRLTYPE enumeration; it is for testing purposes only.</b>

The <b>D3DKMT_TDRDBGCTRLTYPE</b> enumeration type contains values that affect the behavior of the operating system's Timeout Detection and Recovery (TDR) process in a call to the OpenGL <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a> function.


## -enum-fields




### -field D3DKMT_TDRDBGCTRLTYPE_FORCETDR

Simulate a TDR.


### -field D3DKMT_TDRDBGCTRLTYPE_DISABLEBREAK

Disable DebugBreak on timeout.


### -field D3DKMT_TDRDBGCTRLTYPE_ENABLEBREAK

Enable DebugBreak on timeout.


### -field D3DKMT_TDRDBGCTRLTYPE_UNCONDITIONAL

Disables all safety conditions (e.g. check for consecutive recoveries).


### -field D3DKMT_TDRDBGCTRLTYPE_VSYNCTDR

Simulate a Vsync TDR.


### -field D3DKMT_TDRDBGCTRLTYPE_GPUTDR

Simulate a GPU TDR.


### -field D3DKMT_TDRDBGCTRLTYPE_FORCEDODTDR

Simulate a display-only present TDR.

Supported starting with Windows 8.


### -field D3DKMT_TDRDBGCTRLTYPE_FORCEDODVSYNCTDR

Simulate a display-only VSync TDR.

Supported starting with Windows 8.


### -field D3DKMT_TDRDBGCTRLTYPE_ENGINETDR

Simulate an engine TDR.

Supported starting with Windows 8.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a>
 

 

