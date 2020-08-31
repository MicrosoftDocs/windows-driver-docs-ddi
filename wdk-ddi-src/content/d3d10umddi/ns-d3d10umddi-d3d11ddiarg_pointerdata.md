---
UID: NS:d3d10umddi.D3D11DDIARG_POINTERDATA
title: D3D11DDIARG_POINTERDATA (d3d10umddi.h)
description: The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation.
old-location: display\d3d11ddiarg_pointerdata.htm
ms.assetid: 1065079d-ff48-4b68-930c-bbbd3f17d5bd
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_POINTERDATA structure"]
ms.keywords: D3D11DDIARG_POINTERDATA, D3D11DDIARG_POINTERDATA structure [Display Devices], UMDisplayDriver_Dx11param_Structs_4e1d0abb-4385-4d8b-9687-0c913884ab46.xml, d3d10umddi/D3D11DDIARG_POINTERDATA, display.d3d11ddiarg_pointerdata
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_POINTERDATA is supported beginning with the Windows 7 operating system.
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
req.typenames: D3D11DDIARG_POINTERDATA
f1_keywords:
 - D3D11DDIARG_POINTERDATA
 - d3d10umddi/D3D11DDIARG_POINTERDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_POINTERDATA
---

# D3D11DDIARG_POINTERDATA structure


## -description

The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation.

## -struct-fields

### -field uCBOffset

A UINT value that specifies the offset, in bytes, into the constant buffer that the <b>uCBID</b> member specifies to reach the data for the interface. 

Setting this member is equivalent to setting the first 12 bits of a 32-bit value (0x00000FFF).

### -field uCBID

A UINT value that identifies the constant buffer that data for the interface is in. 

Setting this member is equivalent to setting bits 13 through 16 of a 32-bit value (0x0000F000).

### -field uBaseSamp

A UINT value that specifies the index of the first sampler that is used by the class instance of the interface implementation.

Setting this member is equivalent to setting bits 17 through 20 of a 32-bit value (0x000F0000).

### -field uBaseTex

A UINT value that specifies the index of the first texture that is used by the class instance of the interface implementation.

Setting this member is equivalent to setting bits 21 through 27 of a 32-bit value (0x07F00000).

### -field uReserved

Reserved for future use. This member makes the size of D3D11DDIARG_POINTERDATA 32-bit aligned and should always be set to zero. Setting this member to zero is equivalent to setting the remaining 5 bits (0xF8000000) of a 32-bit value to zeros.

## -remarks

D3D11DDIARG_POINTERDATA contains the location of the data for one of the interfaces that is referred to in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">CsSetShaderWithIfaces</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">DsSetShaderWithIfaces</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">GsSetShaderWithIfaces</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">HsSetShaderWithIfaces</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">PsSetShaderWithIfaces</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">VsSetShaderWithIfaces</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">CsSetShaderWithIfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">DsSetShaderWithIfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">GsSetShaderWithIfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">HsSetShaderWithIfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">PsSetShaderWithIfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">VsSetShaderWithIfaces</a>

