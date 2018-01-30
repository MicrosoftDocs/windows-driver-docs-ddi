---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE
title: EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE
author: windows-driver-content
description: A driver's EvtWmiInstanceQueryInstance callback function copies a WMI provider's instance data into a buffer for delivery to a WMI client.
old-location: wdf\evtwmiinstancequeryinstance.htm
old-project: wdf
ms.assetid: 13eed838-2943-4bb4-915f-6a84f0f95851
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtwmiinstancequeryinstance, EvtWmiInstanceQueryInstance callback function, EvtWmiInstanceQueryInstance, EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE, EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE, wdfwmi/EvtWmiInstanceQueryInstance, DFWMIRef_424a0070-8839-4d3f-b285-166b23ac03f7.xml, kmdf.evtwmiinstancequeryinstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfWMI.h
apiname:
-	EvtWmiInstanceQueryInstance
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS"
req.product: Windows 10 or later.
---

# EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiInstanceQueryInstance</i> callback function copies a WMI provider's instance data into a buffer for delivery to a WMI client.


## -prototype


````
EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE EvtWmiInstanceQueryInstance;

NTSTATUS EvtWmiInstanceQueryInstance(
  _In_  WDFWMIINSTANCE WmiInstance,
  _In_  ULONG          OutBufferSize,
  _In_  PVOID          OutBuffer,
  _Out_ PULONG         BufferUsed
)
{ ... }
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object.


### -param OutBufferSize [in]

The size, in bytes, of the output buffer that <i>OutBuffer</i> points to.


### -param OutBuffer [in]

A pointer to the output buffer.


### -param BufferUsed [out]

A pointer to a location that receives the number of bytes that the driver places in the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.  


## -returns


The <i>EvtWmiInstanceQueryInstance</i> callback function must return STATUS_BUFFER_TOO_SMALL, if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data. Otherwise, the callback function must copy data into the buffer and return STATUS_SUCCESS.



## -remarks


To register an <i>EvtWmiInstanceQueryInstance</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>. 

Before the framework sends the driver-supplied instance data to the WMI client, it adds all of the necessary WMI header information to the data.

If your driver sets the <b>UseContextForQuery</b> member of the WMI instance object's <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure to <b>TRUE</b> for a read-only data block, the driver does not provide an <i>EvtWmiInstanceQueryInstance</i> callback function.

If your driver must provide string data to a WMI client, the driver should call the <a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_buffer_append_string.md">WDF_WMI_BUFFER_APPEND_STRING</a> function to format the string.

For more information about the <i>EvtWmiInstanceQueryInstance</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting Read/Write WMI Data Blocks</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting Read-Only WMI Data Blocks</a>. 

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceQueryInstance</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>

<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_buffer_append_string.md">WDF_WMI_BUFFER_APPEND_STRING</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

