---
UID: NC:wdfpdo.EVT_WDF_DEVICE_REPORTED_MISSING
title: EVT_WDF_DEVICE_REPORTED_MISSING (wdfpdo.h)
description: A bus driver's EvtDeviceReportedMissing event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.
old-location: wdf\evtdevicereportedmissing.htm
tech.root: wdf
ms.assetid: F64E2FFD-229F-4447-94C2-A5403E7893B7
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_REPORTED_MISSING callback function"]
ms.keywords: EVT_WDF_DEVICE_REPORTED_MISSING, EVT_WDF_DEVICE_REPORTED_MISSING callback, EvtDeviceReportedMissing, EvtDeviceReportedMissing callback function, kmdf.evtdevicereportedmissing, wdf.evtdevicereportedmissing, wdfpdo/EvtDeviceReportedMissing
f1_keywords:
 - "wdfpdo/EvtDeviceReportedMissing"
 - "EvtDeviceReportedMissing"
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfpdo.h
api_name:
- EvtDeviceReportedMissing
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_REPORTED_MISSING callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   A bus driver's <i>EvtDeviceReportedMissing</i> event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceReportedMissing</i> callback function. To register this callback function, the bus driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls <i>EvtDeviceReportedMissing</i> when processing a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> request for <b>BusRelations</b> from the PnP manager.

Most framework-based bus drivers do not need to provide this callback function.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>
 

 

