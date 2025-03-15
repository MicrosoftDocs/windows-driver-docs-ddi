---
UID: NS:d3dkmthk._D3DKMT_ADAPTERREGISTRYINFO
title: D3DKMT_ADAPTERREGISTRYINFO (d3dkmthk.h)
description: The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.
ms.date: 02/03/2025
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DKMT_ADAPTERREGISTRYINFO
f1_keywords:
 - _D3DKMT_ADAPTERREGISTRYINFO
 - d3dkmthk/_D3DKMT_ADAPTERREGISTRYINFO
 - D3DKMT_ADAPTERREGISTRYINFO
 - d3dkmthk/D3DKMT_ADAPTERREGISTRYINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ADAPTERREGISTRYINFO
 - D3DKMT_ADAPTERREGISTRYINFO
---

# D3DKMT_ADAPTERREGISTRYINFO structure

## -description

The **D3DKMT_ADAPTERREGISTRYINFO** structure contains registry information about the graphics adapter.

## -struct-fields

### -field AdapterString [out]

A string that contains the name of the graphics adapter.

### -field BiosString [out]

A string that contains the name of the BIOS for the graphics adapter.

### -field DacType [out]

A string that contains the DAC type for the graphics adapter.

### -field ChipType [out]

A string that contains the chip type for the graphics adapter.

## -see-also

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

[**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)
