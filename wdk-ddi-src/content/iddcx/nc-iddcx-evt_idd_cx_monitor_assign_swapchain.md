---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
title: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN is called by the OS to inform the driver of a mode change for monitors on the adapter.
old-location: display\evt_idd_cx_monitor_assign_swapchain.htm
old-project: display
ms.assetid: ae3b4101-d006-48ad-91c9-d9b3ee9a4674
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.evt_idd_cx_monitor_assign_swapchain, EvtIddCxMonitorAssignSwapchain callback function [Display Devices], EvtIddCxMonitorAssignSwapchain, EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN, iddcx/EvtIddCxMonitorAssignSwapchain, PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback function pointer [Display Devices], PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	iddcx.h
apiname:
-	PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN callback


## -description


<b>EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</b> is called by the OS to inform the driver of a mode change for monitors on the adapter.


## -prototype


````
EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN EvtIddCxMonitorAssignSwapchain;

NTSTATUS EvtIddCxMonitorAssignSwapchain(
  _In_       IDDCX_MONITOR          MonitorObject,
  _In_ const IDARG_IN_SETSWAPCHAIN* pInArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN;
````


## -parameters




### -param MonitorObject [in]


                    
                A handle provided by the driver used by the OS to identify the monitor that has been affected by the mode change.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</b>.


## -returns



(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    



## -remarks


<div class="alert"><b>Note</b>  <p class="note">The resolution of the surfaces in the swapchain will always be the same resolution as the target mode set.
        The format of the surfaces will be one of the formats supported by the driver, but the format of each acquired buffer may
        change between the formats supported from frame to frame. The driver should check the format of each buffer acquired.

</div><div> </div>

