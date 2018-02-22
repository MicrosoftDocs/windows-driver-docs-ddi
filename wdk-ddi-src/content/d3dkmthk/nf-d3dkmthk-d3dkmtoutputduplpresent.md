---
UID: NF:d3dkmthk.D3DKMTOutputDuplPresent
title: D3DKMTOutputDuplPresent function
author: windows-driver-content
description: Submits a present command from the Desktop Duplication API swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtoutputduplpresent.htm
old-project: display
ms.assetid: d5846165-f58d-44a8-9242-02a2f85d3a8d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DKMTOutputDuplPresent function [Display Devices], D3DKMTOutputDuplPresent, display.d3dkmtoutputduplpresent, PFND3DKMT_OUTPUTDUPLPRESENT, d3dkmthk/D3DKMTOutputDuplPresent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTOutputDuplPresent
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOutputDuplPresent function


## -description


Submits a present command from the <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOutputDuplPresent(
  _In_ const D3DKMT_OUTPUTDUPLPRESENT pData
);
````


## -parameters




### -param D3DKMT_OUTPUTDUPLPRESENT

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputduplpresent.md">D3DKMT_OUTPUTDUPLPRESENT</a> structure that describes parameters for the present operation.


## -returns




       Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The present operation was successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtoutputduplpresent.md">D3DKMTOutputDuplPresent</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The primary surface handle was invalidated because of a display mode change. If the OpenGL installable client driver (ICD) receives this error code, it should reopen or re-create the primary handle, replace all references in the command buffer to the old handle with the new handle, and then resubmit the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
An error occurred on the rendering device context that the <b>hContext</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputduplpresent.md">D3DKMT_OUTPUTDUPLPRESENT</a> specifies. 

<div class="alert"><b>Note</b>    This error code does not indicate the initiation of a Timeout Detection and Recovery (TDR) process or that the GPU stopped responding.</div>
<div> </div>
For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and re-created. The ICD can call the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a> function to determine a more precise reason for the error. 

</td>
</tr>
</table>
 




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputduplpresent.md">D3DKMT_OUTPUTDUPLPRESENT</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOutputDuplPresent function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

