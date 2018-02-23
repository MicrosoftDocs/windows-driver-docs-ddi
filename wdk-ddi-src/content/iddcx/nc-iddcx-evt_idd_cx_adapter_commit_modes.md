---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_COMMIT_MODES
title: EVT_IDD_CX_ADAPTER_COMMIT_MODES
author: windows-driver-content
description: EVT_IDD_CX_ADAPTER_COMMIT_MODES is called by the OS to inform the driver of a mode change for monitors on the adapter.
old-location: display\evt_idd_cx_adapter_commit_modes.htm
old-project: display
ms.assetid: 30e1d240-8a1e-4bcd-8c04-76894ac61624
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.evt_idd_cx_adapter_commit_modes, EvtIddCxAdapterCommitModes callback function [Display Devices], EvtIddCxAdapterCommitModes, EVT_IDD_CX_ADAPTER_COMMIT_MODES, EVT_IDD_CX_ADAPTER_COMMIT_MODES, iddcx/EvtIddCxAdapterCommitModes, PFN_IDD_CX_ADAPTER_COMMIT_MODES callback function pointer [Display Devices], PFN_IDD_CX_ADAPTER_COMMIT_MODES
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
-	PFN_IDD_CX_ADAPTER_COMMIT_MODES
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_ADAPTER_COMMIT_MODES callback


## -description


<b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b> is called by the OS to inform the driver of a mode change for monitors on the adapter.


## -prototype


````
EVT_IDD_CX_ADAPTER_COMMIT_MODES EvtIddCxAdapterCommitModes;

NTSTATUS EvtIddCxAdapterCommitModes(
  _In_       IDDCX_ADAPTER         AdapterObject,
  _In_ const IDARG_IN_COMMITMODES* pInArgs
)
{ ... }

typedef EVT_IDD_CX_ADAPTER_COMMIT_MODES PFN_IDD_CX_ADAPTER_COMMIT_MODES;
````


## -parameters




### -param AdapterObject [in]


                    
                A handle provided by the driver used by the OS to reference the adapter in a call to the driver.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    




## -remarks



The OS always provides the IDDCX_PATH for every connected monitor even if it is not active and indicates which paths have changed.  If a path is marked  inactive, then the whole display pipeline for that path will be powered off and no signal will be sent to the monitor.

<div class="alert"><b>Note</b>  <p class="note">When a new path is committed, the driver should program the display pipeline to display a black image until the first frame is ready to be displayed. To achieve this, WDDM visibility should be off until the first frame is ready to be displayed, then the visibility should be turned on.

</div>
<div> </div>


