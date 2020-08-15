---
UID: NF:wdfpdo.WdfPdoInitSetEventCallbacks
title: WdfPdoInitSetEventCallbacks function (wdfpdo.h)
description: The WdfPdoInitSetEventCallbacks method registers a bus driver's event callback functions.
old-location: wdf\wdfpdoinitseteventcallbacks.htm
tech.root: wdf
ms.assetid: 7ce47eab-c1d7-4a0d-accb-c8a925aa3d1d
ms.date: 02/26/2018
keywords: ["WdfPdoInitSetEventCallbacks function"]
ms.keywords: DFDeviceObjectFdoPdoRef_00002737-467e-4449-8c6c-498860a18747.xml, WdfPdoInitSetEventCallbacks, WdfPdoInitSetEventCallbacks method, kmdf.wdfpdoinitseteventcallbacks, wdf.wdfpdoinitseteventcallbacks, wdfpdo/WdfPdoInitSetEventCallbacks
f1_keywords:
 - "wdfpdo/WdfPdoInitSetEventCallbacks"
 - "WdfPdoInitSetEventCallbacks"
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoInitSetEventCallbacks
targetos: Windows
req.typenames: 
---

# WdfPdoInitSetEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitSetEventCallbacks</b> method registers a bus driver's event callback functions.


## -parameters




### -param DeviceInit 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param DispatchTable 
[in]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure.


## -remarks



The bus driver must allocate a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfPdoInitSetEventCallbacks</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfPdoInitSetEventCallbacks</b> and <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-device-objects-in-a-bus-driver">Creating Device Objects in a Bus Driver</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure and then calls <b>WdfPdoInitSetEventCallbacks</b>.

```cpp
PWDFDEVICE_INIT  pDeviceInit = NULL;
WDF_PDO_EVENT_CALLBACKS  pdoCallbacks;

pDeviceInit = WdfPdoInitAllocate(Device);
WDF_PDO_EVENT_CALLBACKS_INIT(&pdoCallbacks);
pdoCallbacks.EvtDeviceResourceRequirementsQuery = Bus_Pdo_EvtDeviceResourceRequirementsQuery;
WdfPdoInitSetEventCallbacks(
                            pDeviceInit,
                            &pdoCallbacks
                            );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdf_pdo_event_callbacks_init">WDF_PDO_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallocate">WdfPdoInitAllocate</a>
 

 

