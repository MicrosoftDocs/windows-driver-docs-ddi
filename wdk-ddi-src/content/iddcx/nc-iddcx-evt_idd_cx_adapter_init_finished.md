---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_INIT_FINISHED
title: EVT_IDD_CX_ADAPTER_INIT_FINISHED (iddcx.h)
description: EVT_IDD_CX_ADAPTER_INIT_FINISHED is called by the OS to inform the driver that the adapter initialization has completed.
old-location: display\evt_idd_cx_adapter_init_finished.htm
tech.root: display
ms.assetid: cbce9e1b-2f84-4653-8d3d-e5243a1f0eee
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_ADAPTER_INIT_FINISHED callback function"]
ms.keywords: EVT_IDD_CX_ADAPTER_INIT_FINISHED, EVT_IDD_CX_ADAPTER_INIT_FINISHED callback, EvtIddCxAdapterInitFinished, EvtIddCxAdapterInitFinished callback function [Display Devices], PFN_IDD_CX_ADAPTER_INIT_FINISHED, PFN_IDD_CX_ADAPTER_INIT_FINISHED callback function pointer [Display Devices], display.evt_idd_cx_adapter_init_finished, iddcx/EvtIddCxAdapterInitFinished
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
 - EVT_IDD_CX_ADAPTER_INIT_FINISHED
 - iddcx/EVT_IDD_CX_ADAPTER_INIT_FINISHED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_ADAPTER_INIT_FINISHED
---

# EVT_IDD_CX_ADAPTER_INIT_FINISHED callback function


## -description

<b>EVT_IDD_CX_ADAPTER_INIT_FINISHED</b> is called by the OS to inform the driver that the adapter initialization has completed.

## -parameters

### -param AdapterObject 

[in]
A handle provided by the driver used by the OS to reference the adapter in a call to the driver.

### -param pInArgs 

[in]

Input arguments used by <b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b>.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.