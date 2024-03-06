---
UID: NC:d3dkmddi.DXGKDDI_ENDEXCLUSIVEACCESS
title: DXGKDDI_ENDEXCLUSIVEACCESS (d3dkmddi.h)
description: Learn more about the DXGKDDI_ENDEXCLUSIVEACCESS callback function.
ms.date: 08/31/2023
keywords: ["DXGKDDI_ENDEXCLUSIVEACCESS callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_ENDEXCLUSIVEACCESS
 - d3dkmddi/DXGKDDI_ENDEXCLUSIVEACCESS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_ENDEXCLUSIVEACCESS
dev_langs:
 - c++
---

# DXGKDDI_ENDEXCLUSIVEACCESS callback function

## -description

*Dxgkrnl* calls **DxgkDdiEndExclusiveAccess** to notify the kernel-mode driver that an IOMMU domain switch just completed.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter.

### -param pEndExclusiveAccess

[in] Pointer to a [**DXGKARG_ENDEXCLUSIVEACCESS**](ns-d3dkmddi-_dxgkarg_endexclusiveaccess.md) structure that contains the input arguments for **DxgkDdiEndExclusiveAccess**.

## -returns

**DxgkDdiEndExclusiveAccess** should return STATUS_SUCCESS if the operation succeeds. Otherwise, it should return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

*Dxgkrnl* calls **DxgkDdiBeginExclusiveAccess** and **DxgkDdiEndExclusiveAccess** as a pair when an IOMMU domain switch needs to occur. See [**DxgkDdiBeginExclusiveAccess**](nc-d3dkmddi-dxgkddi_beginexclusiveaccess.md) for implementation details.

## -see-also

[**DRIVER_INITIALIZATION_DATA**](../dispmprt/ns-dispmprt-_driver_initialization_data.md)

[**DXGKARG_ENDEXCLUSIVEACCESS**](ns-d3dkmddi-_dxgkarg_endexclusiveaccess.md)

[**DxgkDdiBeginExclusiveAccess**](nc-d3dkmddi-dxgkddi_beginexclusiveaccess.md)
