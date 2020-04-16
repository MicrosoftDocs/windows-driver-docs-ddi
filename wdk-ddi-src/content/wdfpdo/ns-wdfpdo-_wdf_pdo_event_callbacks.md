---
UID: NS:wdfpdo._WDF_PDO_EVENT_CALLBACKS
title: _WDF_PDO_EVENT_CALLBACKS (wdfpdo.h)
description: The WDF_PDO_EVENT_CALLBACKS structure is the dispatch table for a bus driver's event callback functions.
old-location: wdf\wdf_pdo_event_callbacks.htm
tech.root: wdf
ms.assetid: 13cb1da1-0bb7-444e-a0e1-abcac7d0240d
ms.date: 02/26/2018
keywords: ["_WDF_PDO_EVENT_CALLBACKS structure"]
ms.keywords: "*PWDF_PDO_EVENT_CALLBACKS, DFDeviceObjectFdoPdoRef_7a22d0f9-82ea-448e-8272-d3009beea440.xml, PWDF_PDO_EVENT_CALLBACKS, PWDF_PDO_EVENT_CALLBACKS structure pointer, WDF_PDO_EVENT_CALLBACKS, WDF_PDO_EVENT_CALLBACKS structure, _WDF_PDO_EVENT_CALLBACKS, kmdf.wdf_pdo_event_callbacks, wdf.wdf_pdo_event_callbacks, wdfpdo/PWDF_PDO_EVENT_CALLBACKS, wdfpdo/WDF_PDO_EVENT_CALLBACKS"
f1_keywords:
 - "wdfpdo/WDF_PDO_EVENT_CALLBACKS"
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfpdo.h
api_name:
- WDF_PDO_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WDF_PDO_EVENT_CALLBACKS, *PWDF_PDO_EVENT_CALLBACKS
---

# _WDF_PDO_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_PDO_EVENT_CALLBACKS</b> structure is the dispatch table for a bus driver's event callback functions.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceResourcesQuery

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resources_query">EvtDeviceResourcesQuery</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceResourceRequirementsQuery

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resource_requirements_query">EvtDeviceResourceRequirementsQuery</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceEject

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_eject">EvtDeviceEject</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSetLock

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_set_lock">EvtDeviceSetLock</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceEnableWakeAtBus

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_enable_wake_at_bus">EvtDeviceEnableWakeAtBus</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisableWakeAtBus

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_disable_wake_at_bus">EvtDeviceDisableWakeAtBus</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceReportedMissing

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_reported_missing">EvtDeviceReportedMissing</a> event callback function, or <b>NULL</b>. The <b>EvtDeviceReportedMissing</b> member is available in version 1.11 and later versions of KMDF.


## -remarks



The <b>WDF_PDO_EVENT_CALLBACKS</b> structure is used as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

Drivers must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdf_pdo_event_callbacks_init">WDF_PDO_EVENT_CALLBACKS_INIT</a> to initialize this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdf_pdo_event_callbacks_init">WDF_PDO_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>
 

 

