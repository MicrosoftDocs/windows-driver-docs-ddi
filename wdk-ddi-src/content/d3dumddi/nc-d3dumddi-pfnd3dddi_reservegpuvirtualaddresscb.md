---
UID: NC:d3dumddi.PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
title: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB (d3dumddi.h)
description: Learn more about the PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback function.
tech.root: display
ms.date: 07/19/2024
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
 - d3dumddi/PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
---

# PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback function

## -description

The D3D runtime's **pfnReserveGPUVirtualAddressCb** callback reserves an address range in the current process GPU virtual address space. The address range is only reserved, there is no actual memory behind it.

## -parameters

### -param hDevice

[in] A handle to the display device.

### -param unnamedParam2

[in/out] Pointer to a [**D3DDDI_RESERVEGPUVIRTUALADDRESS**](../d3dukmdt/ns-d3dukmdt-d3dddi_reservegpuvirtualaddress.md) structure that describes the operation to perform.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

The user mode driver (UMD) can choose the base GPU virtual address to use for the reservation by specifying a non-NULL value for **BaseAddress**. The video memory manager (*VidMm*) will use the specified range if it's available. If the range intersects with an existing range, the operation fails. UMD can pass a NULL **BaseAddress** to let *VidMm* pick a base address.

When UMD chooses to let *VidMm* pick a base address for the GPU virtual address range, UMD can choose to constrain the range that *VidMm* should consider by specifying non-NULL values for **MinimumAddress** and **MaximumAddress**. *VidMm* will ensure that the allocated GPU virtual address range is entirely contained in the range. UMD can specify only a **MinimumAddress**, where **MaximumAddress** is assumed to be the end of the address space. Or UMD can specify only a **MaximumAddress**, where **MinimumAddress** is assumed to be 0.

When UMD calls **pfnReserveGpuVertualAddrsesCb** with **hAdapter** set to 0, the D3D runtime will set **hAdapter** to the kernel's D3DKMT_HANDLE before calling the [**D3DKMTReserveGpuVirtualAddress**](../d3dkmthk/nf-d3dkmthk-d3dkmtreservegpuvirtualaddress.md) kernel interface.

## -see-also

[**D3DDDI_RESERVEGPUVIRTUALADDRESS**](../d3dukmdt/ns-d3dukmdt-d3dddi_reservegpuvirtualaddress.md)
