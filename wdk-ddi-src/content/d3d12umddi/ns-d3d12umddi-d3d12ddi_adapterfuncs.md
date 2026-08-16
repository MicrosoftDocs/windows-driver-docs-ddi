---
UID: NS:d3d12umddi.D3D12DDI_ADAPTERFUNCS
title: D3D12DDI_ADAPTERFUNCS (d3d12umddi.h)
description: Contains core functions.
old-location: display\d3d12ddi_adapterfuncs.htm
ms.date: 04/16/2018
keywords: ["D3D12DDI_ADAPTERFUNCS structure"]
ms.keywords: D3D12DDI_ADAPTERFUNCS, D3D12DDI_ADAPTERFUNCS structure [Display Devices], d3d12umddi/D3D12DDI_ADAPTERFUNCS, display.d3d12ddi_adapterfuncs
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
tech.root: display
req.typenames: D3D12DDI_ADAPTERFUNCS
f1_keywords:
 - D3D12DDI_ADAPTERFUNCS
 - d3d12umddi/D3D12DDI_ADAPTERFUNCS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_ADAPTERFUNCS
---

# D3D12DDI_ADAPTERFUNCS structure


## -description

Contains adapter functions.

## -struct-fields

### -field pfnCalcPrivateDeviceSize

A function that calculates private device size. See [pfnCalcPrivateDeviceSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatedevicesize.md).

### -field pfnCreateDevice

A function that creates a device. See [pfnCreateDevice](nc-d3d12umddi-pfnd3d12ddi_createdevice_0003.md).

### -field pfnCloseAdapter

A function that closes the adapter.

### -field pfnGetSupportedVersions

A function that gets supported versions.

### -field pfnGetCaps

A function that gets capabilities.

### -field pfnGetOptionalDDITables

A function that gets optional DDI tables.

### -field pfnFillDDITable

A function that fills a DDI table.

### -field pfnDestroyDevice

A function that destroys a device.
