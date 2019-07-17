---
UID: NE:d3dkmdt._DXGKMDT_OPM_INTERLEAVE_FORMAT
title: _DXGKMDT_OPM_INTERLEAVE_FORMAT (d3dkmdt.h)
description: The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal.
old-location: display\dxgkmdt_opm_interleave_format.htm
tech.root: display
ms.assetid: beaee817-5a91-40df-8b29-4750e3c1600e
ms.date: 05/10/2018
ms.keywords: DXGKMDT_OPM_INTERLEAVE_FORMAT, DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration [Display Devices], DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, DmEnums_7b247abd-613b-495b-aea0-d53d9b519525.xml, _DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, display.dxgkmdt_opm_interleave_format
ms.topic: enum
f1_keywords:
 - "d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- d3dkmdt.h
api_name:
- DXGKMDT_OPM_INTERLEAVE_FORMAT
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_INTERLEAVE_FORMAT
---

# _DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration


## -description


The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal. 


## -enum-fields




### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER

Indicates that the video frame has a scan line ordering other than those given in the following constants of this enumeration.


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE

Indicates that each video frame has a scan line ordering that is progressive (that is, not interlaced).


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST

Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the even scan lines are displayed first. 


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST

Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the odd scan lines are displayed first. 


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_actual_output_format">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>
 

 

