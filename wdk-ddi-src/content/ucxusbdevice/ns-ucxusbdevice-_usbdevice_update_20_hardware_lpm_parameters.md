---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
title: "_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS"
author: windows-driver-content
description: Contains parameters for a request to update USB 2.0 link power management (LPM). UCX passes this structure in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_20_hardware_lpm_parameters.htm
old-project: usbref
ms.assetid: B02CB10F-18C9-4E2C-9F30-042588800EA5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure pointer [Buses], USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure [Buses], _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, buses._usbdevice_update_20_hardware_lpm_parameters, ucxusbdevice/P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, ucxusbdevice/_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
product: Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS
req.product: Windows 10 or later.
---

# _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure


## -description


Contains parameters for a request to update USB 2.0 link power management (LPM). UCX passes this structure in the  <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_update.md">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


## -syntax


````
typedef struct _USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS {
  ULONG HardwareLpmEnable  :1;
  ULONG RemoteWakeEnable  :1;
  ULONG HostInitiatedResumeDurationMode  :1;
  ULONG BestEffortServiceLatency  :4;
  ULONG BestEffortServiceLatencyDeep  :4;
  ULONG L1Timeout  :8;
  ULONG Reserved  :13;
} USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS, *P_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS;
````


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

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_failure_flags.md">USBDEVICE_UPDATE_FAILURE_FLAGS</a>



<a href="..\ucxroothub\ns-ucxroothub-_roothub_20port_info.md">ROOTHUB_20PORT_INFO</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update.md">USBDEVICE_UPDATE</a>



 

 


