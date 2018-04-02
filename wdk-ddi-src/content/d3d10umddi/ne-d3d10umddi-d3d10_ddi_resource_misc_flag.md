---
UID: NE:d3d10umddi.D3D10_DDI_RESOURCE_MISC_FLAG
title: D3D10_DDI_RESOURCE_MISC_FLAG
author: windows-driver-content
description: Identifies miscellaneous information about a resource.
old-location: display\d3d10_ddi_resource_misc_flag.htm
old-project: display
ms.assetid: 1de11acf-1571-44ae-9bde-2b417bf615b7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP, D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT, D3D10_DDI_RESOURCE_MISC_FLAG, D3D10_DDI_RESOURCE_MISC_FLAG enumeration [Display Devices], D3D10_DDI_RESOURCE_MISC_REMOTE, D3D10_DDI_RESOURCE_MISC_SHARED, D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT, D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER, D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS, D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED, D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS, D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP, D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER, D3DWDDM1_3DDI_RESOURCE_MISC_TILED, D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL, D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED, D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE, D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED, UMDisplayDriver_Dx10param_Structs_0b144bfc-1cec-4e30-b7c6-f7c2cb7d4567.xml, d3d10umddi/, d3d10umddi/D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP, d3d10umddi/D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT, d3d10umddi/D3D10_DDI_RESOURCE_MISC_FLAG, d3d10umddi/D3D10_DDI_RESOURCE_MISC_REMOTE, d3d10umddi/D3D10_DDI_RESOURCE_MISC_SHARED, d3d10umddi/D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT, d3d10umddi/D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER, d3d10umddi/D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS, d3d10umddi/D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED, d3d10umddi/D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS, d3d10umddi/D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_TILED, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED, display.d3d10_ddi_resource_misc_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_DDI_RESOURCE_MISC_FLAG
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RESOURCE_MISC_FLAG
---

# D3D10_DDI_RESOURCE_MISC_FLAG enumeration


## -description


Identifies miscellaneous information about a resource. 


## -enum-fields




### -field D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP

The resource can be used with the <a href="https://msdn.microsoft.com/abd045f2-9c05-4579-8d80-aba31523157d">GenMips</a> function.


### -field D3D10_DDI_RESOURCE_MISC_SHARED

The resource can be shared by multiple devices and processes.


### -field D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT

The resource is not required to persist across presentations. 
      

For more information about this value, see the Remarks section of the <a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a> reference page.

Supported starting with Windows Server 2008, and Windows Vista with Service Pack 1 (SP1).


### -field D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS

The resource is a buffer that the runtime can use as the argument buffer in a call to the driver's <a href="https://msdn.microsoft.com/3debfb11-4de9-456b-a094-feb2f68e96a5">DrawIndexedInstancedIndirect</a>, <a href="https://msdn.microsoft.com/99520dae-3934-496f-80bf-e5b306554415">DrawInstancedIndirect</a>, or <a href="https://msdn.microsoft.com/0c818515-163f-48ba-ad57-f4405672c98f">DispatchIndirect</a> function.

Supported starting with Windows 7.


### -field D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS

The resource is a buffer on which the driver's <a href="https://msdn.microsoft.com/7ca462c7-ec43-4af7-92c8-ed69e5d324e2">CreateShaderResourceView(D3D11)</a> function can create a raw-format view. A raw-format view is created through a call to the driver's <b>CreateShaderResourceView(D3D11)</b> function with the D3D11_DDI_BUFFEREX_SRV_FLAG_RAW flag set in the <b>BufferEx</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure. Raw-format views allow to read (and write in the case of unordered access view (UAV) objects) up to four DWORD values in one instruction.

Supported starting with Windows 7.

Supported in Windows 7 and later versions.


### -field D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED

The resource is a buffer that has its memory sectioned into equally sized pieces (structures). The structure size of each piece is provided in the resource declaration. The drivers might be able to use this information to optimize memory layout.

Supported starting with Windows 7.


### -field D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP

The resource must consider any resource clamp, which a call to the driver's <a href="https://msdn.microsoft.com/a54b2fa7-c0c2-42b7-ae89-7984282d4af4">SetResourceMinLOD</a> function applies.

Supported starting with Windows 7.


### -field D3D10_DDI_RESOURCE_MISC_REMOTE

This value is for internal use only. Do not use. 


### -field D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT

The resource can contain protected content. This value should be used only if the driver and hardware support content protection.

Supported starting with Windows 8.


### -field D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER

The driver should restrict access to the shared surface. This value should be used only when a shared surface is created. The process that is creating the surface is always allowed to open the shared resource.

Supported starting with Windows 8.


### -field D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER

The resource is a shared cross-adapter resource.

The user-mode display driver should record information about the cross-adapter resource in a private driver data structure. The display miniport driver can call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function  to retrieve this private data.

The DirectX graphics kernel subsystem calls the <a href="https://msdn.microsoft.com/8ee65716-496c-4b0f-baa7-34a625847d5f">DxgkDdiDescribeAllocation</a> function to get information on the cross-adapter resource when it needs to open the resource on another adapter. The display miniport must ensure that this information is correct.

Supported starting with Windows 8.1.


### -field D3DWDDM1_3DDI_RESOURCE_MISC_TILED

The resource is tiled. 

Supported starting with Windows 8.1.


### -field D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL

The resource is a tile pool.  Must be a buffer with <a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a> usage type <b>D3D10_DDI_USAGE_DEFAULT</b>.

Supported starting with Windows 8.1.


### -field D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED

The resource should be created such that it will be protected by the hardware. 

Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE

The resource contains a displayable surface.

Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED

The decoder input buffer contains encrypted protected content. The hardware does not need to protect these buffers (as they are encrypted), but the driver may need to allocate these buffers differently so they can efficiently interact with their decryption hardware.

Supported starting with Windows 10.




## -see-also




<a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a>



<a href="https://msdn.microsoft.com/7ca462c7-ec43-4af7-92c8-ed69e5d324e2">CreateShaderResourceView(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/0c818515-163f-48ba-ad57-f4405672c98f">DispatchIndirect</a>



<a href="https://msdn.microsoft.com/3debfb11-4de9-456b-a094-feb2f68e96a5">DrawIndexedInstancedIndirect</a>



<a href="https://msdn.microsoft.com/99520dae-3934-496f-80bf-e5b306554415">DrawInstancedIndirect</a>



<a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a>



<a href="https://msdn.microsoft.com/abd045f2-9c05-4579-8d80-aba31523157d">GenMips</a>



<a href="https://msdn.microsoft.com/a54b2fa7-c0c2-42b7-ae89-7984282d4af4">SetResourceMinLOD</a>
 

 

