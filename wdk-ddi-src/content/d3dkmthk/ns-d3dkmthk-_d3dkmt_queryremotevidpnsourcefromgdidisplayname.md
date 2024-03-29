---
UID: NS:d3dkmthk._D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
title: _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME (d3dkmthk.h)
description: Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.
old-location: display\d3dkmt_queryremotevidpnsourcefromgdidisplayname.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure"]
ms.keywords: D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure [Display Devices], _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, d3dkmthk/D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, display.d3dkmt_queryremotevidpnsourcefromgdidisplayname
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
f1_keywords:
 - _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
 - d3dkmthk/_D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
 - D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
 - d3dkmthk/D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
 - D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
---

# _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure


## -description

Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.

## -struct-fields

### -field DeviceName [in]

The name of the GDI device on which to open an adapter instance.

### -field VidPnSourceId [out]

The zero-based video present network (VidPN) source identifier for the display device that is represented by the <b>DeviceName</b> member.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryremotevidpnsourcefromgdidisplayname">D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName</a>

