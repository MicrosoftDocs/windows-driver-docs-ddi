---
UID: NS:d3dhal._D3DHAL_CALLBACKS3
title: _D3DHAL_CALLBACKS3 (d3dhal.h)
description: D3DHAL_CALLBACKS3 is one of several callback structures that describe the Direct3D support provided by the driver.
old-location: display\d3dhal_callbacks3.htm
tech.root: display
ms.assetid: 09215332-4ee3-4f7b-be25-091b8d85fd6b
ms.date: 05/10/2018
keywords: ["D3DHAL_CALLBACKS3 structure"]
ms.keywords: "*LPD3DHAL_CALLBACKS3, D3DHAL_CALLBACKS3, D3DHAL_CALLBACKS3 structure [Display Devices], LPD3DHAL_CALLBACKS3, LPD3DHAL_CALLBACKS3 structure pointer [Display Devices], _D3DHAL_CALLBACKS3, d3dhal/D3DHAL_CALLBACKS3, d3dhal/LPD3DHAL_CALLBACKS3, d3dstrct_1171658a-fb5a-45ad-aedc-14fcc9725f60.xml, display.d3dhal_callbacks3"
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: D3DHAL_CALLBACKS3, *LPD3DHAL_CALLBACKS3
f1_keywords:
 - _D3DHAL_CALLBACKS3
 - d3dhal/_D3DHAL_CALLBACKS3
 - LPD3DHAL_CALLBACKS3
 - d3dhal/LPD3DHAL_CALLBACKS3
 - D3DHAL_CALLBACKS3
 - d3dhal/D3DHAL_CALLBACKS3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_CALLBACKS3
---

# _D3DHAL_CALLBACKS3 structure


## -description

D3DHAL_CALLBACKS3 is one of several callback structures that describe the Direct3D support provided by the driver.

## -struct-fields

### -field dwSize

Specifies the size in bytes of this structure.

### -field dwFlags

Indicates the callbacks associated with this structure that the driver has implemented. For every bit the driver sets in <b>dwFlags</b>, the driver must initialize the corresponding function pointer member of this structure. This member can be the bitwise-OR of one or more of the following flags:

| **Flag** | **Meaning** | 
|:--|:--|
| D3DHAL3_CB32_CLEAR2 | Not used in DirectX 7.0 and later versions. | 
| D3DHAL3_CB32_DRAWPRIMITIVES2 | The DrawPrimitives2member points to a driver-implemented [D3dDrawPrimitives2](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb)  callback. | 
| D3DHAL3_CB32_RESERVED | Not used in DirectX 7.0 and later versions. | 
| D3DHAL3_CB32_VALIDATETEXTURESTAGESTATE | The ValidateTextureStageStatemember points to a driver-implemented [D3dValidateTextureStageState](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_validatetexturestagestatecb) callback. |

### -field Clear2

Must be set to <b>NULL</b>. This was a pointer to the driver-supplied <b>D3dClear2</b> callback that is no longer used for DirectX 7.0 and beyond. Instead the driver should respond to the D3DDP2OP_CLEAR command stream token in its implementation of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.

### -field lpvReserved

Specifies a reserved field and must be set to <b>NULL</b> in a Windows 2000 and later driver.

### -field ValidateTextureStageState

Points to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_validatetexturestagestatecb">D3dValidateTextureStageState</a> callback, or <b>NULL</b>. Drivers that support multitexturing must implement the callback that this member points to.

### -field DrawPrimitives2

Points to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback. A driver must implement the callback that this member points to.

## -remarks

The driver allocates this structure and sets appropriate values in all members. The driver's <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a> function returns a pointer to this structure when that function is called with the GUID_D3DCallbacks3 GUID.

## -see-also

D3DDP2OP_CLEAR



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_callbacks">D3DHAL_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_validatetexturestagestatecb">D3dValidateTextureStageState</a>



<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>

