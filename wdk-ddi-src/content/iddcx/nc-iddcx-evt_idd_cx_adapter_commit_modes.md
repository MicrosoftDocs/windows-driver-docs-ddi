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
 - EVT_IDD_CX_ADAPTER_COMMIT_MODES
---

# EVT_IDD_CX_ADAPTER_COMMIT_MODES callback function

## -description

The OS calls **EVT_IDD_CX_ADAPTER_COMMIT_MODES** to inform the driver of a mode change for monitors on the adapter.

## -parameters

### -param AdapterObject

[in] A driver-provided [**IDDCX_ADAPTER**](/windows-hardware/drivers/display/iddcx-objects#iddcx_adapter) handle that is used by the OS to reference the adapter in a call to the driver.

### -param pInArgs

[in] Pointer to a [**IDARG_IN_COMMITMODES**](ns-iddcx-idarg_in_commitmodes.md) structure that contains arguments used by **EVT_IDD_CX_ADAPTER_COMMIT_MODES**.

## -returns

**EVT_IDD_CX_ADAPTER_COMMIT_MODES** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

The OS always provides the [**IDDCX_PATH**](ns-iddcx-iddcx_path.md) for every connected monitor even if that monitor isn't active, and indicates which paths have changed. If a path is marked inactive, then the whole display pipeline for that path will be powered off and no signal will be sent to the monitor.

When a new path is committed, the driver should program the display pipeline to display a black image until the first frame is ready to be displayed. To achieve this, WDDM visibility should be off until the first frame is ready to be displayed, then the visibility should be turned on.

## -see-also

[**IDARG_IN_COMMITMODES**](ns-iddcx-idarg_in_commitmodes.md)
