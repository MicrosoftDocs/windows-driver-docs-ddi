---
UID: NS:dxgiddi.DXGI_DDI_PRIMARY_DESC
title: DXGI_DDI_PRIMARY_DESC (dxgiddi.h)
description: Describes a resource that is used as a primary (that is, a resource that is scanned out to the display).
old-location: display\dxgi_ddi_primary_desc.htm
tech.root: display
ms.assetid: eb6db822-c6d3-43d0-91af-49d19189ed83
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_PRIMARY_DESC, DXGI_DDI_PRIMARY_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_a733016c-aa05-4d79-b13b-96d1bc33dac2.xml, display.dxgi_ddi_primary_desc, dxgiddi/DXGI_DDI_PRIMARY_DESC
ms.topic: struct
f1_keywords:
 - "dxgiddi/DXGI_DDI_PRIMARY_DESC"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxgiddi.h
api_name:
- DXGI_DDI_PRIMARY_DESC
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_PRIMARY_DESC
---

# DXGI_DDI_PRIMARY_DESC structure


## -description


Describes a resource that is used as a primary (that is, a resource that is scanned out to the display). 


## -struct-fields




### -field Flags

[in] A valid bitwise OR of any of the following values that indicates how the resource is displayed. 

| **Value** | **Meaning** | 
|:--|:--|
| DXGI_DDI_PRIMARY_OPTIONAL (0x1) | The user-mode display driver can prevent the resource from ever being a primary.<br/>The driver can prevent the actual flip (from optional primary to regular primary) and can use a copy-style present operation. Therefore, in this way, the driver might be able to prevent the resource from being actually used as a primary. | 
| DXGI_DDI_PRIMARY_NONPREROTATED (0x2) | The primary really represents the DXGI_DDI_MODE_ROTATION_IDENTITY-type rotation, even though it is used with non-DXGI_DDI_MODE_ROTATION_IDENTITY-type display modes, because applications will handle the output orientation by rotating, for example, the viewport and projection matrix. | 
| DXGI_DDI_PRIMARY_STEREO (0x4) | Supported in Windows 8 and later versions.<br/>The primary represents a stereo back buffer. | 
| DXGI_DDI_PRIMARY_INDIRECT (0x8) | Supported in Windows 10 and later versions.<br/>The primary will be used for presenting to an indirect display device. | 



### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the primary surface is created on. 


### -field ModeDesc

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_mode_desc">DXGI_DDI_MODE_DESC</a> structure that describes the display mode. 


### -field DriverFlags

[out] A valid bitwise OR of values that indicate how the driver can display the resource. 

The DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT (0x1) value is currently the only supported value. This bit indicates that the driver cannot support the runtime setting any subresource of the specified resource as a primary. The user-mode display driver should set this bit if it implements presentation from this surface through a copy operation. Therefore, the runtime will not use flip-style presentation if this bit is set. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_mode_desc">DXGI_DDI_MODE_DESC</a>
 

 

