---
UID: NC:d3dkmddi.DXGKDDI_PATCH
title: DXGKDDI_PATCH (d3dkmddi.h)
description: The DxgkDdiPatch function assigns physical addresses to the given direct memory access (DMA) buffer before the DMA buffer is submitted to the graphics hardware.
old-location: display\dxgkddipatch.htm
ms.assetid: 363be784-0e3b-4f9a-a643-80857478bbae
ms.date: 05/10/2018
keywords: ["DXGKDDI_PATCH callback function"]
ms.keywords: DXGKDDI_PATCH, DXGKDDI_PATCH callback, DmFunctions_dc8691fa-b688-4762-a641-93e4625d8931.xml, DxgkDdiPatch, DxgkDdiPatch callback function [Display Devices], d3dkmddi/DxgkDdiPatch, display.dxgkddipatch
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_PATCH
 - d3dkmddi/DXGKDDI_PATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiPatch
product:
 - Windows
---

# DXGKDDI_PATCH callback function


## -description

The <i>DxgkDdiPatch</i> function assigns physical addresses to the given direct memory access (DMA) buffer before the DMA buffer is submitted to the graphics hardware.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pPatch

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_patch">DXGKARG_PATCH</a> structure that describes the DMA buffer to be patched with physical addresses.

## -returns

      Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.

## -remarks

The <i>DxgkDdiPatch</i> function must assign physical addresses to the DMA buffer in place. Therefore, when the display miniport driver generates the DMA buffer, the driver must ensure that space is available in the DMA buffer to insert instructions that are required to handle physical addresses. Note that physical addresses might correspond to video memory, AGP/PCI Express memory, or system memory. 

The driver must examine the supplied patch-location list in the <b>pPatchLocationList</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_patch">DXGKARG_PATCH</a> structure that is pointed to by the <i>pPatch</i> parameter to identify places in the DMA buffer that must be patched with physical addresses. The supplied allocation list (which is specified by the <b>pAllocationList</b> member of DXGKARG_PATCH) also contains the physical addresses that the video memory manager generates. The call to the driver's <i>DxgkDdiPatch</i> function is the last chance for the driver to modify the content of the DMA buffer before the DMA buffer is submitted to the graphics processing unit (GPU). Note that the driver can patch a DMA buffer multiple times in scenarios where the DMA buffer is preempted.

The driver can patch the value that is supplied in the <b>SubmissionFenceId</b> member of DXGKARG_PATCH into the fence command at the end of the DMA buffer. For more information about this member, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supplying-fence-identifiers">Supplying Fence Identifiers</a>.

If the driver returns an error code, the Microsoft DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x3</li>
<li>A pointer to an internal scheduler data structure</li>
<li>A pointer to an internal scheduler data structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>
<i>DxgkDdiPatch</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_patch">DXGKARG_PATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

