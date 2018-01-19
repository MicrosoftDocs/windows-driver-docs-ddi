---
UID: NF:d3dkmthk.D3DKMTPresent
title: D3DKMTPresent function
author: windows-driver-content
description: The D3DKMTPresent function submits a present command to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtpresent.htm
old-project: display
ms.assetid: 5821ecef-d90b-4b3f-87cd-1b80b86f2671
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTPresent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTPresent
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTPresent function



## -description
The <b>D3DKMTPresent</b> function submits a present command to the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).



## -syntax

````
NTSTATUS APIENTRY D3DKMTPresent(
  _In_ const D3DKMT_PRESENT *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present.md">D3DKMT_PRESENT</a> structure that describes parameters for presenting.


## -returns
<b>D3DKMTPresent</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The present was successfully performed.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display context was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtpresent.md">D3DKMTPresent</a> could not complete because of insufficient memory.
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_INVALID</b></dt>
</dl>The primary surface handle was invalidated because of a display mode change. If the OpenGL installable client driver (ICD) receives this error code, it should reopen or re-create the primary handle, replace all references in the command buffer to the old handle with the new handle, and then resubmit the buffer.
<dl>
<dt><b>STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE</b></dt>
</dl>An error occurred on the rendering device context that the <b>hContext</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present.md">D3DKMT_PRESENT</a> specifies. 

For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and re-created. The ICD can call the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a> function to determine a more precise reason for the error. 

 

This function might also return other NTSTATUS values.


## -remarks
The <b>D3DKMTPresent</b> function might return STATUS_INVALID_PARAMETER, depending on the combination of parameter values (that is, values in members of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present.md">D3DKMT_PRESENT</a> structure that <i>pData</i> points to). The following list describes the most common combinations of parameter values that might cause <b>D3DKMTPresent</b> to return STATUS_INVALID PARAMETER:

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTPresent</b> to present data.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present.md">D3DKMT_PRESENT</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplaymode.md">D3DKMTSetDisplayMode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTPresent function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

