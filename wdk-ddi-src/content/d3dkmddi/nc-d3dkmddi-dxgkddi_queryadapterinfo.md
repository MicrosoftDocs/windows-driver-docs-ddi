---
UID: NC:d3dkmddi.DXGKDDI_QUERYADAPTERINFO
title: DXGKDDI_QUERYADAPTERINFO (d3dkmddi.h)
description: Learn more about the DXGKDDI_QUERYADAPTERINFO callback function.
ms.date: 02/03/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_QUERYADAPTERINFO
 - d3dkmddi/DXGKDDI_QUERYADAPTERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_QUERYADAPTERINFO
dev_langs:
 - c++
---

# DXGKDDI_QUERYADAPTERINFO callback function

## -description

*Dxgkrnl* calls the display miniport driver's (KMD's) **DxgkDdiQueryAdapterInfo** function to retrieve configuration information from the graphics adapter.

## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pQueryAdapterInfo [in]

A pointer to a [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) structure that the KMD fills with the configuration information for the graphics adapter.

## -returns

**DxgkDdiQueryAdapterInfo** returns STATUS_SUCCESS when it successfully retrieves the configuration information. Otherwise, it returns an NTSTATUS code such as one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER        | One or more passed parameter contained errors that prevented it from completing.|
| STATUS_NO_MEMORY                | **DxgkDdiQueryAdapterInfo** couldn't allocate memory that was required for it to complete.|
| STATUS_GRAPHICS_DRIVER_MISMATCH | The KMD isn't compatible with the user-mode display driver (UMD) that initiated the call to **DxgkDdiQueryAdapterInfo** (that is, supplied private data for a query to the KMD). |

## -remarks

When the UMD calls the Direct3D runtime's [**pfnQueryAdapterInfoCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md) callback, a call to the **DxgkDdiQueryAdapterInfo** function is initiated.

* If *Dxgkrnl* specifies DXGKQAITYPE_UMDRIVERPRIVATE in [**DXGKARG_QUERYADAPTERINFO::Type**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md), **pOutputData** points to a proprietary structure that KMD fills with the configuration information that is necessary for the UMD to identify the adapter.

* If *Dxgkrnl* specifies DXGKQAITYPE_DRIVERCAPS in **DXGKARG_QUERYADAPTERINFO::Type**, the KMD should populate the provided [**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md) structure with information that the subsystem can use.

* If *Dxgkrnl* specifies DXGKQAITYPE_QUERYSEGMENT in **DXGKARG_QUERYADAPTERINFO::Type**, the KMD should provide information about the memory segments that it supports. For more information about memory segments, see [Initializing Use of Memory Segments](/windows-hardware/drivers/display/initializing-use-of-memory-segments).

**DxgkDdiQueryAdapterInfo** should be made pageable.

All drivers that support WDDM 2.6 and greater must implement the **DxgkDdiQueryAdapterInfo** callback.

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**pfnQueryAdapterInfoCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md)
