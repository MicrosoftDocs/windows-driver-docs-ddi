---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
title: EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD (wdfwmi.h)
description: A driver's EvtWmiInstanceExecuteMethod callback function executes a specified method that the driver provides for a WMI data provider's instance.
old-location: wdf\evtwmiinstanceexecutemethod.htm
tech.root: wdf
ms.assetid: b14de1d7-0df2-46d1-a3bd-c23f33d3ed75
ms.date: 02/26/2018
keywords: ["EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback function"]
ms.keywords: DFWMIRef_d54dc0b0-bdef-40a7-b863-5946f4d8e5f5.xml, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback, EvtWmiInstanceExecuteMethod, EvtWmiInstanceExecuteMethod callback function, kmdf.evtwmiinstanceexecutemethod, wdf.evtwmiinstanceexecutemethod, wdfwmi/EvtWmiInstanceExecuteMethod
f1_keywords:
 - "wdfwmi/EvtWmiInstanceExecuteMethod"
 - "EvtWmiInstanceExecuteMethod"
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
- EvtWmiInstanceExecuteMethod
targetos: Windows
req.typenames: 
---

# EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtWmiInstanceExecuteMethod</i> callback function executes a specified method that the driver provides for a WMI data provider's instance.


## -parameters




### -param WmiInstance 
[in]
A handle to a WMI instance object.


### -param MethodId 
[in]
A value that identifies a method in a provider instance. This value corresponds to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wmi-property-qualifiers">WmiMethodId</a> value that is specified in the provider's MOF file.


### -param InBufferSize 
[in]
The number of bytes of input data.


### -param OutBufferSize 
[in]
The number of bytes of output data that the buffer that <i>Buffer</i> points to can hold.


### -param Buffer 
[in, out]
A pointer to a buffer that is used for input, output, or both, as determined by the specified method. If both input and output data are provided, the driver overwrites the input data with the output data.


### -param BufferUsed 
[out]
A pointer to a location that receives the number of bytes that the driver wrote into the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.  


## -returns



The <i>EvtWmiInstanceExecuteMethod</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. The driver must return STATUS_BUFFER_TOO_SMALL if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data.




## -remarks



To register an <i>EvtWmiInstanceExecuteMethod</i> callback function, your driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>. 

After a driver executes the instance method that the <i>MethodId</i> parameter specifies, the driver must use the <i>BufferUsed</i> parameter to store the number of bytes that were written to the buffer.

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceExecuteMethod</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceExecuteMethod</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_query_instance">EvtWmiInstanceQueryInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_instance">EvtWmiInstanceSetInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_item">EvtWmiInstanceSetItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>
 

 

