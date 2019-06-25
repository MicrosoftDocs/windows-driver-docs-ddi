---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
title: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN (iddcx.h)
description: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN is called by the OS to inform the driver of a mode change for monitors on the adapter.
old-location: display\evt_idd_cx_monitor_assign_swapchain.htm
tech.root: display
ms.assetid: ae3b4101-d006-48ad-91c9-d9b3ee9a4674
ms.date: 05/10/2018
ms.keywords: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback, EvtIddCxMonitorAssignSwapchain, EvtIddCxMonitorAssignSwapchain callback function [Display Devices], PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function pointer [Display Devices], display.evt_idd_cx_monitor_assign_swapchain, iddcx/EvtIddCxMonitorAssignSwapchain
ms.topic: callback
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
req.irql: "_requires_same_"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function


## -description


<b>EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</b> is called by the OS to inform the driver of a mode change for monitors on the adapter.


## -parameters




### -param MonitorObject [in]


A handle provided by the driver used by the OS to identify the monitor that has been affected by the mode change.


### -param pInArgs [in]

Input arguments used by <b>EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 
                    




## -remarks



<div class="alert"><b>Note</b>  <p class="note">The resolution of the surfaces in the swapchain will always be the same resolution as the target mode set.
        The format of the surfaces will be one of the formats supported by the driver, but the format of each acquired buffer may
        change between the formats supported from frame to frame. The driver should check the format of each buffer acquired.

</div>
<div> </div>


