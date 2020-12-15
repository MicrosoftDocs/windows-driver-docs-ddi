---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
title: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE (iddcx.h)
description: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE is called by the OS to get the size of an OPM certificate.
old-location: display\evt_idd_cx_monitor_opm_get_certificate_size.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE, EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback, EvtIddCxMonitorOpmGetCertificateSize, EvtIddCxMonitorOpmGetCertificateSize callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE, PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_get_certificate_size, iddcx/EvtIddCxMonitorOpmGetCertificateSize
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
 - EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
 - iddcx/EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
---

# EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback function


## -description

<b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b> is called by the OS to get the size of an OPM certificate.

## -parameters

### -param AdapterObject 

[in]
The object for the adapter that the OPM certificate size will be gotten for.

### -param pInArgs 

[in]
Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b>.

### -param pOutArgs 

[out]
Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b>.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
