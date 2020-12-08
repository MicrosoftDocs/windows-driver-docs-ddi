---
UID: NS:d3dkmddi._DXGKARG_CREATEDEVICE
title: _DXGKARG_CREATEDEVICE (d3dkmddi.h)
description: The DXGKARG_CREATEDEVICE structure describes a graphics context device.
old-location: display\dxgkarg_createdevice.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_CREATEDEVICE structure"]
ms.keywords: "*INOUT_PDXGKARG_CREATEDEVICE, DXGKARG_CREATEDEVICE, DXGKARG_CREATEDEVICE structure [Display Devices], DmStructs_76bb50f9-b0d8-415c-b183-ad780ebcabc6.xml, _DXGKARG_CREATEDEVICE, d3dkmddi/DXGKARG_CREATEDEVICE, display.dxgkarg_createdevice"
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
req.typenames: DXGKARG_CREATEDEVICE
f1_keywords:
 - _DXGKARG_CREATEDEVICE
 - d3dkmddi/_DXGKARG_CREATEDEVICE
 - DXGKARG_CREATEDEVICE
 - d3dkmddi/DXGKARG_CREATEDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_CREATEDEVICE
---

# _DXGKARG_CREATEDEVICE structure


## -description

The DXGKARG_CREATEDEVICE structure describes a graphics context device.

## -struct-fields

### -field hDevice

A handle to the graphics context device. On input to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function, <b>hDevice</b> specifies the handle that the driver should use when it calls back into the Microsoft DirectX graphics kernel subsystem. 

The driver generates a unique handle and passes it back to the DirectX graphics subsystem. On output from the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function, <b>hDevice</b> specifies the handle that the DirectX graphics subsystem should use in subsequent driver calls to identify the device.

### -field Flags

 A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_createdeviceflags">DXGK_CREATEDEVICEFLAGS</a> structure that identifies how to create the device.

### -field pInfo

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_deviceinfo">DXGK_DEVICEINFO</a> structure that contains parameters that the DirectX graphics subsystem requires from the display miniport driver.

### -field Pasid

The owner process PASID for a support vector machine GPU.

Supported starting with Windows 10.

### -field hKmdProcess

A handle to the corresponding kernel mode driver process object.

Supported starting with Windows 10.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_createdeviceflags">DXGK_CREATEDEVICEFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_deviceinfo">DXGK_DEVICEINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>
