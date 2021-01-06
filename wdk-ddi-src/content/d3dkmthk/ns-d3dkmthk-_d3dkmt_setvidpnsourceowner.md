---
UID: NS:d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER
title: _D3DKMT_SETVIDPNSOURCEOWNER (d3dkmthk.h)
description: The D3DKMT_SETVIDPNSOURCEOWNER structure describes the parameters for setting or releasing the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmt_setvidpnsourceowner.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_SETVIDPNSOURCEOWNER structure"]
ms.keywords: D3DKMT_SETVIDPNSOURCEOWNER, D3DKMT_SETVIDPNSOURCEOWNER structure [Display Devices], OpenGL_Structs_942045f1-1a3a-4c4a-b533-ec70fcad6d8f.xml, _D3DKMT_SETVIDPNSOURCEOWNER, d3dkmthk/D3DKMT_SETVIDPNSOURCEOWNER, display.d3dkmt_setvidpnsourceowner
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETVIDPNSOURCEOWNER
f1_keywords:
 - _D3DKMT_SETVIDPNSOURCEOWNER
 - d3dkmthk/_D3DKMT_SETVIDPNSOURCEOWNER
 - D3DKMT_SETVIDPNSOURCEOWNER
 - d3dkmthk/D3DKMT_SETVIDPNSOURCEOWNER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_SETVIDPNSOURCEOWNER
---

# _D3DKMT_SETVIDPNSOURCEOWNER structure


## -description

The D3DKMT_SETVIDPNSOURCEOWNER structure describes the parameters for setting or releasing the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## -struct-fields

### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that acquires or releases the VidPN source owner.

### -field pType

[in] An array of owner types. Elements of the array can contain the following values from the D3DKMT_VIDPNSOURCEOWNER_TYPE enumeration type.

|Value|Meaning|
|--- |--- |
|D3DKMT_VIDPNSOURCEOWNER_UNOWNED (0)|No owner, or GDI is the owner.|
|D3DKMT_VIDPNSOURCEOWNER_SHARED (1)|A shared owner. That is, the owner can yield to any exclusive owner. This type is not available to legacy devices.|
|D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVE (2)|An exclusive owner without shared GDI primary.|
|D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVEGDI (3)|An exclusive owner with shared GDI primary. This owner must exclusively own all of the VidPn sources. This type is available only to legacy devices.|

### -field pVidPnSourceId

[in] An array of zero-based identification numbers of the video present sources in paths of a video present network (VidPN) topology.

### -field VidPnSourceCount

The number of valid entries in the array that <b>pVidPnSourceId</b> specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetvidpnsourceowner">D3DKMTSetVidPnSourceOwner</a>
