---
UID: NC:wdfwmi.EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
title: EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL (wdfwmi.h)
description: A driver's EvtWmiProviderFunctionControl callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.
old-location: wdf\evtwmiproviderfunctioncontrol.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback function"]
ms.keywords: DFWMIRef_2beaafe2-cb59-49cb-85dc-6ea2beff1b1e.xml, EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL, EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback, EvtWmiProviderFunctionControl, EvtWmiProviderFunctionControl callback function, kmdf.evtwmiproviderfunctioncontrol, wdf.evtwmiproviderfunctioncontrol, wdfwmi/EvtWmiProviderFunctionControl
req.header: wdfwmi.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
 - wdfwmi/EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfWMI.h
api_name:
 - EvtWmiProviderFunctionControl
---

# EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtWmiProviderFunctionControl</i> callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.

## -parameters

### -param WmiProvider 

[in]
A handle to a WMI provider object.

### -param Control 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_control">WDF_WMI_PROVIDER_CONTROL</a>-typed value that identifies a capability that the driver must enable or disable.

### -param Enable 

[in]
A Boolean value that, if <b>TRUE</b>, indicates that the driver must enable the capability that <i>Control</i> specifies. If <b>FALSE</b>, the driver must disable the capability.

## -returns

The <i>EvtWmiProviderFunctionControl</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, it must return a status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>.

## -remarks

To register an <i>EvtWmiProviderFunctionControl</i> callback function, your driver must place the function's address in a <a href="/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure before it calls <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>. 

If your driver sets the <b>WdfWmiProviderExpensive</b> flag in the <b>Flags</b> member of a WMI data provider's <a href="/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure, and if the driver provides an <i>EvtWmiProviderFunctionControl</i> callback function, the framework calls the callback function when the driver should enable or disable its ability to collect WMI data. 

Instead of providing an <i>EvtWmiProviderFunctionControl</i> callback function, the driver can call <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiproviderisenabled">WdfWmiProviderIsEnabled</a> to find out if it should enable or disable collecting data.

For more information about the <i>EvtWmiProviderFunctionControl</i> callback function, see <a href="/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_execute_method">EvtWmiInstanceExecuteMethod</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_query_instance">EvtWmiInstanceQueryInstance</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_instance">EvtWmiInstanceSetInstance</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_item">EvtWmiInstanceSetItem</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_control">WDF_WMI_PROVIDER_CONTROL</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiproviderisenabled">WdfWmiProviderIsEnabled</a>
