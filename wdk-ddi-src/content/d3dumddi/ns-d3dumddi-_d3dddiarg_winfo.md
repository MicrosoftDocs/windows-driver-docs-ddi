---
UID: NS:d3dumddi._D3DDDIARG_WINFO
title: _D3DDDIARG_WINFO (d3dumddi.h)
description: The D3DDDIARG_WINFO structure describes a w range for w buffering.
old-location: display\d3dddiarg_winfo.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_WINFO structure"]
ms.keywords: D3DDDIARG_WINFO, D3DDDIARG_WINFO structure [Display Devices], UMDisplayDriver_param_Structs_6ab282fa-6a76-4712-83d5-77638adb2b7a.xml, _D3DDDIARG_WINFO, d3dumddi/D3DDDIARG_WINFO, display.d3dddiarg_winfo
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDIARG_WINFO
f1_keywords:
 - _D3DDDIARG_WINFO
 - d3dumddi/_D3DDDIARG_WINFO
 - D3DDDIARG_WINFO
 - d3dumddi/D3DDDIARG_WINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_WINFO
 - D3DDDIARG_WINFO
---

# _D3DDDIARG_WINFO structure


## -description

The D3DDDIARG_WINFO structure describes a w range for w buffering.

## -struct-fields

### -field WNear

[in] A FLOAT value that indicates the near limit in the w range.

### -field WFar

[in] A FLOAT value that indicates the far limit in the w range.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updatewinfo">UpdateWInfo</a>

