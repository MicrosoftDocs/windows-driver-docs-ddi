---
UID: NE:d3dukmdt._D3DDDI_POOL
title: _D3DDDI_POOL (d3dukmdt.h)
description: The D3DDDI_POOL enumeration type contains values that identify particular types of memory pool.
old-location: display\d3dddi_pool.htm
tech.root: display
ms.assetid: b3f34183-7595-47b6-a2f1-c32650734a04
ms.date: 05/10/2018
keywords: ["D3DDDI_POOL enumeration"]
ms.keywords: D3DDDIPOOL_LOCALVIDMEM, D3DDDIPOOL_NONLOCALVIDMEM, D3DDDIPOOL_STAGINGMEM, D3DDDIPOOL_SYSTEMMEM, D3DDDIPOOL_VIDEOMEMORY, D3DDDI_POOL, D3DDDI_POOL enumeration [Display Devices], D3D_other_Structs_859cbea4-6000-4906-a3f4-3ff6ea4caa7b.xml, _D3DDDI_POOL, d3dukmdt/D3DDDIPOOL_LOCALVIDMEM, d3dukmdt/D3DDDIPOOL_NONLOCALVIDMEM, d3dukmdt/D3DDDIPOOL_STAGINGMEM, d3dukmdt/D3DDDIPOOL_SYSTEMMEM, d3dukmdt/D3DDDIPOOL_VIDEOMEMORY, d3dukmdt/D3DDDI_POOL, display.d3dddi_pool
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
req.typenames: D3DDDI_POOL
f1_keywords:
 - _D3DDDI_POOL
 - d3dukmdt/_D3DDDI_POOL
 - D3DDDI_POOL
 - d3dukmdt/D3DDDI_POOL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_POOL
---

# _D3DDDI_POOL enumeration


## -description

The D3DDDI_POOL enumeration type contains values that identify particular types of memory pool.

## -enum-fields

### -field D3DDDIPOOL_SYSTEMMEM

Resources exist in system memory.

### -field D3DDDIPOOL_VIDEOMEMORY

Resources exist in display memory.

### -field D3DDDIPOOL_LOCALVIDMEM

Resources exist in true, local display memory rather than nonlocal display memory (for example, AGP memory).

### -field D3DDDIPOOL_NONLOCALVIDMEM

Resources exist in nonlocal display memory (for example, AGP memory) rather than true, local display memory.

### -field D3DDDIPOOL_STAGINGMEM

Resources exist in staging memory that the user-mode display driver has allocated. This value indicates to the driver that it should allocate its own staging memory rather than use allocated Direct3D 10Level 9 memory.

Must be supported by WDDM 1.3 and later drivers. Available starting with Windows 8.1.

## -remarks

Pool memory types are defined as an enumeration type rather than separate flags because the types are all mutually exclusive.

Note that the D3DDDIPOOL_LOCALVIDMEM and D3DDDIPOOL_NONLOCALVIDMEM values are provided as hints to the user-mode display driver so it can improve performance. For more information about these values, see <a href="/windows-hardware/drivers/display/specifying-memory-type-for-a-resource">Specifying Memory Type for a Resource</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>