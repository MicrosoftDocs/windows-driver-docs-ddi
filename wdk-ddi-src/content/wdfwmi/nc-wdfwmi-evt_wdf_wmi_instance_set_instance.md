---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_SET_INSTANCE
title: EVT_WDF_WMI_INSTANCE_SET_INSTANCE (wdfwmi.h)
description: A driver's EvtWmiInstanceSetInstance callback function sets all of a WMI data provider's instance data to values that a WMI client supplies.
old-location: wdf\evtwmiinstancesetinstance.htm
tech.root: wdf
ms.assetid: defd33c5-90ae-40c9-9123-7c3de2c77f35
ms.date: 02/26/2018
keywords: ["EVT_WDF_WMI_INSTANCE_SET_INSTANCE callback function"]
ms.keywords: DFWMIRef_28837d36-7a7e-4468-adbc-826bf4c75ef0.xml, EVT_WDF_WMI_INSTANCE_SET_INSTANCE, EVT_WDF_WMI_INSTANCE_SET_INSTANCE callback, EvtWmiInstanceSetInstance, EvtWmiInstanceSetInstance callback function, kmdf.evtwmiinstancesetinstance, wdf.evtwmiinstancesetinstance, wdfwmi/EvtWmiInstanceSetInstance
f1_keywords:
 - "wdfwmi/EvtWmiInstanceSetInstance"
 - "EvtWmiInstanceSetInstance"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfWMI.h
api_name:
- EvtWmiInstanceSetInstance
targetos: Windows
req.typenames: 
---

# EVT_WDF_WMI_INSTANCE_SET_INSTANCE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtWmiInstanceSetInstance</i> callback function sets all of a WMI data provider's instance data to values that a WMI client supplies.


## -parameters




### -param WmiInstance 
[in]
A handle to a WMI instance object.


### -param InBufferSize 
[in]
The size, in bytes, of the input buffer that <i>InBuffer</i> points to.


### -param InBuffer 
[in]
A pointer to the input buffer.


## -returns



The <i>EvtWmiInstanceSetInstance</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. If the input buffer that the <i>InBuffer</i> parameter points to is too small to contain all of the data that the driver expects, the callback function must return STATUS_WMI_SET_FAILURE.




## -remarks



To register an <i>EvtWmiInstanceSetInstance</i> callback function, your driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>. 

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceSetInstance</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceSetInstance</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_execute_method">EvtWmiInstanceExecuteMethod</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_query_instance">EvtWmiInstanceQueryInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_item">EvtWmiInstanceSetItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>
 

 

