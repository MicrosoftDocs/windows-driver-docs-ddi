---
UID: NS:d3d12umddi.D3D12DDIARG_CREATEDEVICE_0003
title: D3D12DDIARG_CREATEDEVICE_0003 (d3d12umddi.h)
description: The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.
old-location: display\d3d12ddiarg_createdevice_0003.htm
ms.date: 05/10/2018
keywords: ["D3D12DDIARG_CREATEDEVICE_0003 structure"]
ms.keywords: D3D12DDIARG_CREATEDEVICE_0003, D3D12DDIARG_CREATEDEVICE_0003 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATEDEVICE_0003, display.d3d12ddiarg_createdevice_0003
req.header: d3d12umddi.h
req.include-header: 
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
req.typenames: D3D12DDIARG_CREATEDEVICE_0003
f1_keywords:
 - D3D12DDIARG_CREATEDEVICE_0003
 - d3d12umddi/D3D12DDIARG_CREATEDEVICE_0003
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATEDEVICE_0003
---

# D3D12DDIARG_CREATEDEVICE_0003 structure


## -description

The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.

## -struct-fields

### -field hRTDevice

[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime.

### -field Interface

[in] The Direct3D interface version.

### -field Version

[in] A UINT value that the driver can use to identify when the Direct3D runtime was built (the runtime version).

### -field pKTCallbacks

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.

### -field hDrvDevice

 A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.

### -field p12UMCallbacks

 A pointer to a D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality.

### -field p12UMCallbacks_0022

A pointer to a [D3D12DDI_CORELAYER_DEVICECALLBACKS_0022](ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md) structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality.

### -field p12UMCallbacks_0050

A pointer to a [D3D12DDI_CORELAYER_DEVICECALLBACKS_0050](ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0050.md) structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality.

### -field Flags

Flag values that identify how to create the display device.
