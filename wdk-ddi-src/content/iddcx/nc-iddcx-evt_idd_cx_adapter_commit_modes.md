---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_COMMIT_MODES
title: EVT_IDD_CX_ADAPTER_COMMIT_MODES (iddcx.h)
description: EVT_IDD_CX_ADAPTER_COMMIT_MODES is called by the OS to inform the driver of a mode change for monitors on the adapter.
old-location: display\evt_idd_cx_adapter_commit_modes.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_ADAPTER_COMMIT_MODES callback function"]
ms.keywords: EVT_IDD_CX_ADAPTER_COMMIT_MODES, EVT_IDD_CX_ADAPTER_COMMIT_MODES callback, EvtIddCxAdapterCommitModes, EvtIddCxAdapterCommitModes callback function [Display Devices], PFN_IDD_CX_ADAPTER_COMMIT_MODES, PFN_IDD_CX_ADAPTER_COMMIT_MODES callback function pointer [Display Devices], display.evt_idd_cx_adapter_commit_modes, iddcx/EvtIddCxAdapterCommitModes
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
 - EVT_IDD_CX_ADAPTER_COMMIT_MODES
 - iddcx/EVT_IDD_CX_ADAPTER_COMMIT_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_ADAPTER_COMMIT_MODES
---

# EVT_IDD_CX_ADAPTER_COMMIT_MODES callback function


## -description

<b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b> is called by the OS to inform the driver of a mode change for monitors on the adapter.

## -parameters

### -param AdapterObject 

[in]
A handle provided by the driver used by the OS to reference the adapter in a call to the driver.

### -param pInArgs 

[in]
Input arguments used by <b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b>.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The OS always provides the IDDCX_PATH for every connected monitor even if it is not active and indicates which paths have changed.  If a path is marked  inactive, then the whole display pipeline for that path will be powered off and no signal will be sent to the monitor.

<div class="alert"><b>Note</b>  <p class="note">When a new path is committed, the driver should program the display pipeline to display a black image until the first frame is ready to be displayed. To achieve this, WDDM visibility should be off until the first frame is ready to be displayed, then the visibility should be turned on.

</div>
<div> </div>
