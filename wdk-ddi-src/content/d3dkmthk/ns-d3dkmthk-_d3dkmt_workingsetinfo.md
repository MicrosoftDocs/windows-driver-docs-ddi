---
UID: NS:d3dkmthk._D3DKMT_WORKINGSETINFO
title: _D3DKMT_WORKINGSETINFO (d3dkmthk.h)
description: The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_workingsetinfo.htm
ms.assetid: 1a5b75e4-abdd-4916-b2b5-4dbb53a525ae
ms.date: 05/10/2018
keywords: ["D3DKMT_WORKINGSETINFO structure"]
ms.keywords: D3DKMT_WORKINGSETINFO, D3DKMT_WORKINGSETINFO structure [Display Devices], OpenGL_Structs_a3992911-10eb-48fe-a755-fe14e68fbaa8.xml, _D3DKMT_WORKINGSETINFO, d3dkmthk/D3DKMT_WORKINGSETINFO, display.d3dkmt_workingsetinfo
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
req.typenames: D3DKMT_WORKINGSETINFO
f1_keywords:
 - _D3DKMT_WORKINGSETINFO
 - d3dkmthk/_D3DKMT_WORKINGSETINFO
 - D3DKMT_WORKINGSETINFO
 - d3dkmthk/D3DKMT_WORKINGSETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_WORKINGSETINFO
---

# _D3DKMT_WORKINGSETINFO structure


## -description

The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a> function.

## -struct-fields

### -field Flags

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_workingsetflags">D3DKMT_WORKINGSETFLAGS</a> structure that indicates, in bit-field flags, working-set properties.

### -field MinimumWorkingSetPercentile

[out] The minimum working-set percentile.

### -field MaximumWorkingSetPercentile

[out] The maximum working-set percentile.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_workingsetflags">D3DKMT_WORKINGSETFLAGS</a>

