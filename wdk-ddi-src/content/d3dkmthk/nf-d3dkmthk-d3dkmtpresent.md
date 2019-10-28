---
UID: NF:d3dkmthk.D3DKMTPresent
title: D3DKMTPresent function (d3dkmthk.h)
description: The D3DKMTPresent function submits a present command to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtpresent.htm
ms.assetid: 5821ecef-d90b-4b3f-87cd-1b80b86f2671
ms.date: 05/10/2018
ms.keywords: D3DKMTPresent, D3DKMTPresent function [Display Devices], OpenGL_Functions_2a9f80c6-84c7-41bb-be78-02640430226d.xml, d3dkmthk/D3DKMTPresent, display.d3dkmtpresent
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTPresent"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTPresent
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTPresent function

## -description

The <b>D3DKMTPresent</b> function submits a present command to the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).

## -parameters

### -param Arg1

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure that describes parameters for presenting.

## -returns

<b>D3DKMTPresent</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The present was successfully performed. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display context was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTPresent](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtpresent)  could not complete because of insufficient memory. | 
| **STATUS_GRAPHICS_ALLOCATION_INVALID** | The primary surface handle was invalidated because of a display mode change. If the OpenGL installable client driver (ICD) receives this error code, it should reopen or re-create the primary handle, replace all references in the command buffer to the old handle with the new handle, and then resubmit the buffer. | 
| **STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE** | An error occurred on the rendering device context that the hContext member of [D3DKMT_PRESENT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present) specifies.<br/>**Note** This error code does not indicate the initiation of a Timeout Detection and Recovery (TDR) process or that the GPU stopped responding.<br/>For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and re-created. The ICD can call the [D3DKMTGetDeviceState](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetdevicestate) function to determine a more precise reason for the error. | 

This function might also return other NTSTATUS values.

## -remarks

The <b>D3DKMTPresent</b> function might return STATUS_INVALID_PARAMETER, depending on the combination of parameter values (that is, values in members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure that <i>pData</i> points to). The following list describes the most common combinations of parameter values that might cause <b>D3DKMTPresent</b> to return STATUS_INVALID PARAMETER:

<ul>
<li>The <b>hDestination</b> member is non-<b>NULL</b> and at least one of the following conditions is true:<ul>
<li>The <b>pSrcSubRects</b> member is <b>NULL</b>.</li>
<li>The <b>SubRectCnt</b> member is 0.</li>
<li>The <b>Blt</b> bit-field flag of the <b>Flags</b> member is not set.</li>
<li>The <b>SrcRectValid</b> bit-field flag of <b>Flags</b> is not set.</li>
<li>The <b>ColorFill</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>Flip</b>, <b>FlipDoNotFlip</b>, <b>FlipDoNotWait</b>, or <b>FlipRestart</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>SrcColorKey</b> or <b>DstColorKey</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>hSource</b> member is equal to <b>hDestination</b>.</li>
<li>The source and destination are not a primary surface.</li>
</ul>
</li>
<li>The <b>Flip</b> bit-field flag of <b>Flags</b> is set and at least one of the following conditions is true:<ul>
<li>The <b>ColorFill</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>Blt</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>SrcColorKey</b> or <b>DstColorKey</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>SrcRectValid</b> or <b>DstRectValid</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>Rotate</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>RestrictVidPnSource</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The source is not a primary surface.</li>
<li>The display miniport driver does not support the flip interval that the <b>FlipInterval</b> member specifies.</li>
<li>The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a> function was not previously called.</li>
</ul>
</li>
<li>The <b>ColorFill</b> bit-field flag of <b>Flags</b> is set and one of the following conditions is true:<ul>
<li><b>pSrcSubRects</b> is <b>NULL</b>.</li>
<li><b>SubRectCnt</b> is 0.</li>
<li>The <b>Blt</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>Flip</b>, <b>FlipDoNotFlip</b>, <b>FlipDoNotWait</b>, or <b>FlipRestart</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>SrcColorKey</b> or <b>DstColorKey</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>SrcRectValid</b> bit-field flag of <b>Flags</b> is set.</li>
</ul>
</li>
<li>The <b>Blt</b> bit-field flag of <b>Flags</b> is set and one of the following conditions is true:<ul>
<li><b>pSrcSubRects</b> is <b>NULL</b>.</li>
<li><b>SubRectCnt</b> is 0.</li>
<li>The <b>ColorFill</b> bit-field flag of <b>Flags</b> is set.</li>
<li>The <b>Flip</b>, <b>FlipDoNotFlip</b>, <b>FlipDoNotWait</b>, or <b>FlipRestart</b> bit-field flag of <b>Flags</b> is set.</li>
</ul>
</li>
</ul>

#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTPresent</b> to present data.

```cpp
HRESULT Present(D3DKMT_HANDLE hDevice, 
                HWND hWnd, 
                RECT* pSrcRect,
                 RECT* pDstRect)
{
    D3DKMT_PRESENT PresentData = {0};

    PresentData.hDevice = hDevice;
    PresentData.Flags.Blt = 
    PresentData.Flags.DstRectValid = 
    PresentData.Flags.SrcRectValid = TRUE;
    PresentData.hWindow = hWnd;
    PresentData.DstRect = *pDstRect;
    PresentData.SrcRect = *pSrcRect;
    PresentData.SubRectCnt = 1;  
    PresentData.pSrcSubRects = pSrcRect; 

    if (NT_SUCCESS((*pfnKTPresent)(&PresentData))) {
        return S_OK;
    }
    return E_FAIL;
}
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetdevicestate">D3DKMTGetDeviceState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a>
 

 

