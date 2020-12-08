---
UID: NF:wdfqueryinterface.WDF_QUERY_INTERFACE_CONFIG_INIT
title: WDF_QUERY_INTERFACE_CONFIG_INIT function (wdfqueryinterface.h)
description: The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure.
old-location: wdf\wdf_query_interface_config_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_QUERY_INTERFACE_CONFIG_INIT function"]
ms.keywords: DFDeviceObjectDriverDefIntRef_d7e26200-d711-4c81-92d6-d2c2c1f052b0.xml, WDF_QUERY_INTERFACE_CONFIG_INIT, WDF_QUERY_INTERFACE_CONFIG_INIT function, kmdf.wdf_query_interface_config_init, wdf.wdf_query_interface_config_init, wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG_INIT
req.header: wdfqueryinterface.h
req.include-header: Wdf.h
req.target-type: Universal
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_QUERY_INTERFACE_CONFIG_INIT
 - wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfqueryinterface.h
api_name:
 - WDF_QUERY_INTERFACE_CONFIG_INIT
---

# WDF_QUERY_INTERFACE_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b> function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.

## -parameters

### -param InterfaceConfig 

[out]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.

### -param Interface 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.

### -param InterfaceType 

[in]
A pointer to the GUID that identifies the interface.

### -param EvtDeviceProcessQueryInterfaceRequest 

[in, optional]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.

## -remarks

For more information about driver-defined interfaces, see <a href="/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>
