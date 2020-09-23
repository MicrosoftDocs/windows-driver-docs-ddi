---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
title: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER (iddcx.h)
description: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER is called by the OS to get an OPM random number.
old-location: display\evt_idd_cx_monitor_opm_get_random_number.htm
tech.root: display
ms.assetid: 330dc0a1-d9a9-44c1-9d29-752c2567e745
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER, EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER callback, EvtIddCxMonitorOpmGetRandomNumber, EvtIddCxMonitorOpmGetRandomNumber callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER, PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_get_random_number, iddcx/EvtIddCxMonitorOpmGetRandomNumber
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
 - EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
 - iddcx/EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
---

# EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER callback function


## -description

<b>EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER</b> is called by the OS to get an OPM random number.

## -parameters

### -param OpmCxtObject 

[in]
The object for the OPM context that a random number will be gotten from.

### -param pOutArgs 

[out]
Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER</b>.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.