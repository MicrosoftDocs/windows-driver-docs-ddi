---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMAND
title: DXGKDDI_SUBMITCOMMAND (d3dkmddi.h)
description: Learn more about the DxgkDdiSubmitCommand callback function.
ms.date: 03/23/2023
keywords: ["DXGKDDI_SUBMITCOMMAND callback function"]
ms.keywords: DXGKDDI_SUBMITCOMMAND, DXGKDDI_SUBMITCOMMAND callback, DmFunctions_c23ba706-a779-4a0d-9977-1f99cecb5217.xml, DxgkDdiSubmitCommand, DxgkDdiSubmitCommand callback function [Display Devices], d3dkmddi/DxgkDdiSubmitCommand, display.dxgkddisubmitcommand
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - DXGKDDI_SUBMITCOMMAND
 - d3dkmddi/DXGKDDI_SUBMITCOMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SUBMITCOMMAND
product:
 - Windows
---

# DXGKDDI_SUBMITCOMMAND callback function

## -description

The **DxgkDdiSubmitCommand** function submits a direct memory access (DMA) buffer to the hardware command execution unit.

## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pSubmitCommand [in]

A pointer to a [**DXGKARG_SUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_submitcommand.md) structure that describes the DMA buffer that the display miniport driver submits to the hardware command execution unit.

## -returns

**DxgkDdiSubmitCommand** returns **STATUS_SUCCESS** upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. See Remarks.

## -remarks

Because paging operations are considered system operations, they are not associated with a specific application context or graphics context. Therefore, when the submission is for a paging operation, the **DxgkDdiSubmitCommand** function is called with **NULL** specified in the **hDevice** member of the [**DXGKARG_SUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_submitcommand.md) structure that the **pSubmitCommand** parameter points to.

However, if the architecture of a particular hardware and driver must have a device internally, the driver must internally create the device during adapter initialization and must keep the device internally as the system default device for use in paging operations.

The driver can write the value that is supplied in the **SubmissionFenceId** member of DXGKARG_SUBMITCOMMAND into the fence command in the ring buffer. For more information about fence commands, see [Supplying Fence Identifiers](/windows-hardware/drivers/display/supplying-fence-identifiers).

If the driver returns an error code, the DirectX graphics kernel subsystem causes a system bugcheck to occur. In a crash dump file, the error is noted by the message [**BugCheck 0x119**](/windows-hardware/drivers/debugger/bug-check-0x119---video-scheduler-internal-error), which will have the following four parameters.

* 0x2 (identifies the cause of the error)
* The NTSTATUS error code returned from the failed driver call
* A pointer to the [**DXGKARG_SUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_submitcommand.md) structure
* A pointer to an internal scheduler data structure

**DxgkDdiSubmitCommand** should be made nonpageable because it runs at IRQL = DISPATCH_LEVEL.

## -see-also

[**DXGKARG_SUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_submitcommand.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)
