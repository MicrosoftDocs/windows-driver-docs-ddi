---
UID: NS:d3dumddi._D3DDDIARG_CREATEDEVICE
title: "_D3DDDIARG_CREATEDEVICE"
author: windows-driver-content
description: The D3DDDIARG_CREATEDEVICE structure contains information that describes the display device to create.
old-location: display\d3dddiarg_createdevice.htm
old-project: display
ms.assetid: 18be278c-2d69-472b-9baf-7c35f8abe879
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_CREATEDEVICE, D3DDDIARG_CREATEDEVICE structure [Display Devices], UMDisplayDriver_param_Structs_42cad924-5200-4737-9d17-4464767f9e93.xml, _D3DDDIARG_CREATEDEVICE, d3dumddi/D3DDDIARG_CREATEDEVICE, display.d3dddiarg_createdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_CREATEDEVICE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEDEVICE
---

# _D3DDDIARG_CREATEDEVICE structure


## -description


The D3DDDIARG_CREATEDEVICE structure contains information that describes the display device to create.


## -struct-fields




### -field hDevice

[in/out] A handle to the display device (graphics context). On input to the <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function, <b>hDevice</b> specifies the handle that the driver should use when it calls back into the Microsoft Direct3D runtime. 

The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function, <b>hDevice</b> specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the display device.


### -field Interface

[in] The Direct3D/DirectDraw interface version (for example, 7, 8, or 9) that creates the device. 


### -field Version

[in] A number that the driver can use to identify when the Direct3D/DirectDraw runtime was built. For example, the driver can use the version number to differentiate between a runtime that is released with Windows Vista and a runtime that is released with a subsequent service pack, which might contain a fix that the driver requires. 


### -field pCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use.


### -field pCommandBuffer

[in] Obsolete. To receive a pointer to the first buffer that the user-mode display driver can use to batch commands, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.


### -field CommandBufferSize

[in] Obsolete.


### -field pAllocationList

[in] Obsolete. To receive an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a> structures for the starting allocation list, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.


### -field AllocationListSize

[in] Obsolete.


### -field pPatchLocationList

[in] Obsolete. To receive an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures for the starting patch-location list, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.


### -field PatchLocationListSize

[in] Obsolete.


### -field pDeviceFuncs


      [out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.
     


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544507">D3DDDI_CREATEDEVICEFLAGS</a> structure that identifies how to create the device. 


### -field CommandBuffer

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544507">D3DDDI_CREATEDEVICEFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>
 

 

