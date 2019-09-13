---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMAND
title: DXGKDDI_SUBMITCOMMAND (d3dkmddi.h)
description: The DxgkDdiSubmitCommand function submits a direct memory access (DMA) buffer to the hardware command execution unit.
old-location: display\dxgkddisubmitcommand.htm
ms.assetid: de1925ab-e444-4cf6-acd9-8fdab26afcec
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SUBMITCOMMAND, DXGKDDI_SUBMITCOMMAND callback, DmFunctions_c23ba706-a779-4a0d-9977-1f99cecb5217.xml, DxgkDdiSubmitCommand, DxgkDdiSubmitCommand callback function [Display Devices], d3dkmddi/DxgkDdiSubmitCommand, display.dxgkddisubmitcommand
ms.topic: callback
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
req.irql: DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiSubmitCommand"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiSubmitCommand
product:
 - Windows
---

# DXGKDDI_SUBMITCOMMAND callback function

## -description

The <i>DxgkDdiSubmitCommand</i> function submits a direct memory access (DMA) buffer to the hardware command execution unit.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pSubmitCommand

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommand">DXGKARG_SUBMITCOMMAND</a> structure that describes the DMA buffer that the display miniport driver submits to the hardware command execution unit.

## -returns

      Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.

## -remarks

Because paging operations are considered system operations, they are not associated with a specific application context or graphics context. Therefore, when the submission is for a paging operation, the <i>DxgkDdiSubmitCommand</i> function is called with <b>NULL</b> specified in the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommand">DXGKARG_SUBMITCOMMAND</a> structure that the <i>pSubmitCommand</i> parameter points to. 

However, if the architecture of a particular hardware and driver must have a device internally, the driver must internally create the device during adapter initialization and must keep the device internally as the system default device for use in paging operations.

The driver can write the value that is supplied in the <b>SubmissionFenceId</b> member of DXGKARG_SUBMITCOMMAND into the fence command in the ring buffer. For more information about fence commands, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supplying-fence-identifiers">Supplying Fence Identifiers</a>.

If the driver returns an error code, the Microsoft DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x2</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommand">DXGKARG_SUBMITCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>
<i>DxgkDdiSubmitCommand</i> should be made nonpageable because it runs at IRQL = DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommand">DXGKARG_SUBMITCOMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

