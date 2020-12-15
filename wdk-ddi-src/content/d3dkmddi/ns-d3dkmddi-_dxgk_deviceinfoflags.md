---
UID: NS:d3dkmddi._DXGK_DEVICEINFOFLAGS
title: _DXGK_DEVICEINFOFLAGS (d3dkmddi.h)
description: The DXGK_DEVICEINFOFLAGS structure identifies, in bit-field flags, information about a graphics device.
old-location: display\dxgk_deviceinfoflags.htm
ms.date: 05/10/2018
keywords: ["DXGK_DEVICEINFOFLAGS structure"]
ms.keywords: DXGK_DEVICEINFOFLAGS, DXGK_DEVICEINFOFLAGS structure [Display Devices], DmStructs_69e769da-b68e-4df6-94dd-95e11bc88b0c.xml, _DXGK_DEVICEINFOFLAGS, d3dkmddi/DXGK_DEVICEINFOFLAGS, display.dxgk_deviceinfoflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.typenames: DXGK_DEVICEINFOFLAGS
f1_keywords:
 - _DXGK_DEVICEINFOFLAGS
 - d3dkmddi/_DXGK_DEVICEINFOFLAGS
 - DXGK_DEVICEINFOFLAGS
 - d3dkmddi/DXGK_DEVICEINFOFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_DEVICEINFOFLAGS
---

# _DXGK_DEVICEINFOFLAGS structure


## -description

The DXGK_DEVICEINFOFLAGS structure identifies, in bit-field flags, information about a graphics device.

## -struct-fields

### -field GuaranteedDmaBufferContract

[out] Obsolete. A UINT value that specifies whether the device that is created through a call to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> uses the guaranteed contract model for direct memory access (DMA) buffers. For more information about the guaranteed contract model, see <a href="/windows-hardware/drivers/display/using-the-guaranteed-contract-dma-buffer-model">Using the Guaranteed Contract DMA Buffer Model</a>. If this member is set, the device uses the guaranteed contract model; if this member is not set, the device does not use the guaranteed contract model. The display driver model for Windows Vista currently supports only the guaranteed contract DMA buffer model. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

[out] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

[out] A member in the union that DXGK_DEVICEINFOFLAGS contains that can hold a 32-bit value that indicates information about a graphics device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_deviceinfo">DXGK_DEVICEINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>
