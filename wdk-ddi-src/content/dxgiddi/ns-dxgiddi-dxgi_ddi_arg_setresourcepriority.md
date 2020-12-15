---
UID: NS:dxgiddi.DXGI_DDI_ARG_SETRESOURCEPRIORITY
title: DXGI_DDI_ARG_SETRESOURCEPRIORITY (dxgiddi.h)
description: The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource.
old-location: display\dxgi_ddi_arg_setresourcepriority.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_SETRESOURCEPRIORITY structure"]
ms.keywords: DXGI_DDI_ARG_SETRESOURCEPRIORITY, DXGI_DDI_ARG_SETRESOURCEPRIORITY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_fda8895f-9cc7-496b-ae2e-bf6b076fc0b3.xml, display.dxgi_ddi_arg_setresourcepriority, dxgiddi/DXGI_DDI_ARG_SETRESOURCEPRIORITY
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
req.typenames: DXGI_DDI_ARG_SETRESOURCEPRIORITY
f1_keywords:
 - DXGI_DDI_ARG_SETRESOURCEPRIORITY
 - dxgiddi/DXGI_DDI_ARG_SETRESOURCEPRIORITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxgiddi.h
api_name:
 - DXGI_DDI_ARG_SETRESOURCEPRIORITY
---

# DXGI_DDI_ARG_SETRESOURCEPRIORITY structure


## -description

The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource.

## -struct-fields

### -field hDevice

[in] A handle to the display device (graphics context) on which the driver sets the eviction-from-memory priority for a resource. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device.

### -field hResource

[in] A handle to the resource to set the priority level for.

### -field Priority

[in] The priority level to set for the resource that the <b>hResource</b> member specifies. A resource's priority level can be set anywhere in the range from 0 through 0xFFFFFFFF.

## -remarks

The priority level that a resource is set at determines its eviction order from memory. A resource that is assigned a low priority is evicted before a resource with a high priority. If two resources have the same priority, the resource that was used more recently is kept in memory; the other resource is evicted.

## -see-also

<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">SetResourcePriorityDXGI</a>
