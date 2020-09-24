---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
title: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN (iddcx.h)
description: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN is called by the OS to inform the driver of a mode change for monitors on the adapter.
old-location: display\evt_idd_cx_monitor_assign_swapchain.htm
tech.root: display
ms.assetid: ae3b4101-d006-48ad-91c9-d9b3ee9a4674
ms.date: 09/24/2020
keywords: ["EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback, EvtIddCxMonitorAssignSwapchain, EvtIddCxMonitorAssignSwapchain callback function [Display Devices], PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function pointer [Display Devices], display.evt_idd_cx_monitor_assign_swapchain, iddcx/EvtIddCxMonitorAssignSwapchain
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
 - iddcx/EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
---

# EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function

## -description

**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN** is called by the OS to inform the indirect display driver (IDD) of a mode change for monitors on the adapter.

## -parameters

### -param MonitorObject

[in] An opaque, driver-created IDDCX_MONITOR handle used by the OS to identify the monitor that has been affected by the mode change.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_SETSWAPCHAIN**](ns-iddcx-idarg_in_setswapchain.md) structure containing information for the driver to use to set the indirect swapchain.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. If an error occurs, the IDD should return **STATUS_GRAPHICS_INDIRECT_DISPLAY_ABANDON_SWAPCHAIN** if there is a good chance that the error will not occur again. Otherwise, it should return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code. See Remarks.

## -remarks

The OS calls **EvtIddCxMonitorAssignSwapChain** so that the IDD can setup its frame processing mechanism. For example, an IDD might create a new thread to initialize D3D devices and then loop on processing frames (see the [ID driver sample](https://github.com/microsoft/Windows-driver-samples/tree/master/video/IndirectDisplay)).

If **EvtIddCxMonitorAssignSwapChain** returns success, the IDD then owns the **IDARG_IN_SETSWAPCHAIN.hSwapChain** object and is responsible for calling [**WdfObjectDelete**](/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete) to release the swapchain object when it stops processing frames. The swapchain processing can stop processing frames when [**EvtIddCxMonitorUnassignSwapChain**](/windows-hardware/drivers/ddi/iddcx/nc-iddcx-evt_idd_cx_monitor_unassign_swapchain) is called or when an error occurs in the frame processing loop after success is returned to **EvtIddCxMonitorAssignSwapChain**. This applies to both console and remote ID adapters and all IddCx versions.

Starting with Windows 10, version 1903, to reduce user impact (for example, time spent waiting for IddCx to bugcheck the driver), IddCx will immediately
bugcheck the driver if **EvtIddCxMonitorAssignSwapChain** reports an error code other than **STATUS_GRAPHICS_INDIRECT_DISPLAY_ABANDON_SWAPCHAIN**.  

If the driver returns **STATUS_GRAPHICS_INDIRECT_DISPLAY_ABANDON_SWAPCHAIN**, IddCx will inform the desktop compositor. A new swapchain needs to be created, so the OS will again call **EvtIddCxMonitorAssignSwapChain**. An ID driver should use this return code only if there is a good chance the error that just occurred will not occur again. That is, an ID driver should not leave users with an unusable desktop because it returned the error code yet did nothing to ensure the same failure will not occur again. For example, if a driver encounters an error while creating the D3D device on the render adapter it could call [**IddCxAdapterSetRenderAdapter**](/windows-hardware/drivers/ddi/iddcx/nf-iddcx-iddcxadaptersetrenderadapter) to change to another adapter (perhaps another GPU or WARP) and then return **STATUS_GRAPHICS_INDIRECT_DISPLAY_ABANDON_SWAPCHAIN**. The OS will create a new swapchain on the new render adapter and hopefully avoid the error. Although this error code is defined starting with Windows 10 version 1903, an ID driver can return this error code on previous OS releases resulting in no effect.

The resolution of the surfaces in the swapchain will always be the same resolution as the target mode set.

The format of the surfaces will be one of the formats supported by the driver, but the format of each acquired buffer can change between the formats supported from frame to frame. The driver should check the format of each buffer acquired.

## -see-also

[**EvtIddCxMonitorUnassignSwapChain**](/windows-hardware/drivers/ddi/iddcx/nc-iddcx-evt_idd_cx_monitor_unassign_swapchain)

[**IDARG_IN_SETSWAPCHAIN**](ns-iddcx-idarg_in_setswapchain.md)
