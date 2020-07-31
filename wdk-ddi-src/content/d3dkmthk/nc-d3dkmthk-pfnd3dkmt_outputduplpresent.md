---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLPRESENT
title: PFND3DKMT_OUTPUTDUPLPRESENT (d3dkmthk.h)
description: Submits a present command from the Desktop Duplication API swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtoutputduplpresent.htm
ms.assetid: d5846165-f58d-44a8-9242-02a2f85d3a8d
ms.date: 05/10/2018
keywords: ["PFND3DKMT_OUTPUTDUPLPRESENT callback function"]
ms.keywords: D3DKMTOutputDuplPresent, D3DKMTOutputDuplPresent callback function [Display Devices], PFND3DKMT_OUTPUTDUPLPRESENT, PFND3DKMT_OUTPUTDUPLPRESENT callback, d3dkmthk/D3DKMTOutputDuplPresent, display.d3dkmtoutputduplpresent
f1_keywords:
 - "d3dkmthk/D3DKMTOutputDuplPresent"
 - "D3DKMTOutputDuplPresent"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- UserDefined
api_location:
- D3dkmthk.h
api_name:
- D3DKMTOutputDuplPresent
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_OUTPUTDUPLPRESENT callback function

## -description

Submits a present command from the <a href="https://docs.microsoft.com/windows/desktop/direct3ddxgi/desktop-dup-api">Desktop Duplication API</a> swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).

## -parameters

### -param Arg1

*pData* 

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_outputduplpresent">D3DKMT_OUTPUTDUPLPRESENT</a> structure that describes parameters for the present operation.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The present operation was successfully performed. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display context was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTOutputDuplPresent](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplpresent) could not complete because of insufficient memory. | 
| **STATUS_GRAPHICS_ALLOCATION_INVALID** | The primary surface handle was invalidated because of a display mode change. If the OpenGL installable client driver (ICD) receives this error code, it should reopen or re-create the primary handle, replace all references in the command buffer to the old handle with the new handle, and then resubmit the buffer. | 
| **STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE** | An error occurred on the rendering device context that the hContext member of [D3DKMT_OUTPUTDUPLPRESENT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_outputduplpresent) specifies.<br/>**Note:** This error code does not indicate the initiation of a Timeout Detection and Recovery (TDR) process or that the GPU stopped responding.<br/>For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and re-created. The ICD can call the [D3DKMTGetDeviceState](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetdevicestate)  function to determine a more precise reason for the error. | 

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetdevicestate">D3DKMTGetDeviceState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_outputduplpresent">D3DKMT_OUTPUTDUPLPRESENT</a>
 

 

