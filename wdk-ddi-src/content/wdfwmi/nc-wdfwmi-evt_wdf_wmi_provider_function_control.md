---
UID: NC:wdfwmi.EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
title: EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
author: windows-driver-content
description: A driver's EvtWmiProviderFunctionControl callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.
old-location: wdf\evtwmiproviderfunctioncontrol.htm
old-project: wdf
ms.assetid: 89b48747-d3aa-48c7-825c-94545f378f07
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtwmiproviderfunctioncontrol, EvtWmiProviderFunctionControl callback function, EvtWmiProviderFunctionControl, EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL, EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL, wdfwmi/EvtWmiProviderFunctionControl, DFWMIRef_2beaafe2-cb59-49cb-85dc-6ea2beff1b1e.xml, kmdf.evtwmiproviderfunctioncontrol
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
-	EvtWmiProviderFunctionControl
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiProviderFunctionControl</i> callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.


## -prototype


````
EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL EvtWmiProviderFunctionControl;

NTSTATUS EvtWmiProviderFunctionControl(
  _In_ WDFWMIPROVIDER           WmiProvider,
  _In_ WDF_WMI_PROVIDER_CONTROL Control,
  _In_ BOOLEAN                  Enable
)
{ ... }
````


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object.


### -param Control [in]

A <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>-typed value that identifies a capability that the driver must enable or disable.


### -param Enable [in]

A Boolean value that, if <b>TRUE</b>, indicates that the driver must enable the capability that <i>Control</i> specifies. If <b>FALSE</b>, the driver must disable the capability.


## -returns


The <i>EvtWmiProviderFunctionControl</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, it must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. 



## -remarks


To register an <i>EvtWmiProviderFunctionControl</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure before it calls <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>. 

If your driver sets the <b>WdfWmiProviderExpensive</b> flag in the <b>Flags</b> member of a WMI data provider's <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure, and if the driver provides an <i>EvtWmiProviderFunctionControl</i> callback function, the framework calls the callback function when the driver should enable or disable its ability to collect WMI data. 

Instead of providing an <i>EvtWmiProviderFunctionControl</i> callback function, the driver can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a> to find out if it should enable or disable collecting data.

For more information about the <i>EvtWmiProviderFunctionControl</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>

<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

