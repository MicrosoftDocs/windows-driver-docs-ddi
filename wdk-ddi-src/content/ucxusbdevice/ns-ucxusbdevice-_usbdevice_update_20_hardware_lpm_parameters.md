---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
title: _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS (ucxusbdevice.h)
description: Contains parameters for a request to update USB 2.0 link power management (LPM). UCX passes this structure in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_20_hardware_lpm_parameters.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure"]
ms.keywords: P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure pointer [Buses], USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure [Buses], _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, buses._usbdevice_update_20_hardware_lpm_parameters, ucxusbdevice/P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, ucxusbdevice/_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
f1_keywords:
 - _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
 - ucxusbdevice/_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
 - USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
 - ucxusbdevice/USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
 - USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
---

# _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure


## -description

Contains parameters for a request to update USB 2.0 link power management (LPM). UCX passes this structure in the  <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_update">EVT_UCX_USBDEVICE_UPDATE</a> callback function.

## -struct-fields

### -field HardwareLpmEnable

If set, indicates are request to enable hardware LPM.

### -field RemoteWakeEnable

If set, indicates are request to enable remote wake signal.

### -field HostInitiatedResumeDurationMode

The requested resume period.

### -field BestEffortServiceLatency

The requested best effort service latency.

### -field BestEffortServiceLatencyDeep

The requested best effort service latency deep.

### -field L1Timeout

The requested L1 timeout.

### -field Reserved

Do not use.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_20port_info">ROOTHUB_20PORT_INFO</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update">USBDEVICE_UPDATE</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update_failure_flags">USBDEVICE_UPDATE_FAILURE_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update_flags">USBDEVICE_UPDATE_FLAGS</a>

