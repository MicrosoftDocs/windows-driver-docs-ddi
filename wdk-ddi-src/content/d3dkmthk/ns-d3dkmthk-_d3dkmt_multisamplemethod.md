---
UID: NS:d3dkmthk._D3DKMT_MULTISAMPLEMETHOD
title: _D3DKMT_MULTISAMPLEMETHOD (d3dkmthk.h)
description: The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.
old-location: display\d3dkmt_multisamplemethod.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_MULTISAMPLEMETHOD structure"]
ms.keywords: D3DKMT_MULTISAMPLEMETHOD, D3DKMT_MULTISAMPLEMETHOD structure [Display Devices], OpenGL_Structs_0617065f-aa53-4b1a-9a3f-e135972d4852.xml, _D3DKMT_MULTISAMPLEMETHOD, d3dkmthk/D3DKMT_MULTISAMPLEMETHOD, display.d3dkmt_multisamplemethod
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
req.typenames: D3DKMT_MULTISAMPLEMETHOD
f1_keywords:
 - _D3DKMT_MULTISAMPLEMETHOD
 - d3dkmthk/_D3DKMT_MULTISAMPLEMETHOD
 - D3DKMT_MULTISAMPLEMETHOD
 - d3dkmthk/D3DKMT_MULTISAMPLEMETHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_MULTISAMPLEMETHOD
 - D3DKMT_MULTISAMPLEMETHOD
---

# _D3DKMT_MULTISAMPLEMETHOD structure


## -description

The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.

## -struct-fields

### -field NumSamples

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).

### -field NumQualityLevels

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range extends from zero through the reported maximum quality setting.

### -field Reserved

Reserved for internal use.

## -remarks

The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires, with the condition that each incremental step noticeably improves the quality of the presented image.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetmultisamplemethodlist">D3DKMTGetMultisampleMethodList</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist">D3DKMT_GETMULTISAMPLEMETHODLIST</a>

