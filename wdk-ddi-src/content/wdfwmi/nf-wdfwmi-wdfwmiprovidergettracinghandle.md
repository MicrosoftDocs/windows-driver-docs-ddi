---
UID: NF:wdfwmi.WdfWmiProviderGetTracingHandle
title: WdfWmiProviderGetTracingHandle function
author: windows-driver-content
description: The WdfWmiProviderGetTracingHandle method returns a handle to the event logger of a WPP software tracing session.
old-location: wdf\wdfwmiprovidergettracinghandle.htm
old-project: wdf
ms.assetid: 44ab1cf3-abd3-4100-a6ad-51f2322881b1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_eea0d3ab-8fb8-4053-8260-e5c396a06524.xml, WdfWmiProviderGetTracingHandle, WdfWmiProviderGetTracingHandle method, kmdf.wdfwmiprovidergettracinghandle, wdf.wdfwmiprovidergettracinghandle, wdfwmi/WdfWmiProviderGetTracingHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfWmiProviderGetTracingHandle
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiProviderGetTracingHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiProviderGetTracingHandle</b> method returns a handle to the event logger of a <a href="https://msdn.microsoft.com/dab776b3-bac9-4157-a530-6e48868ba900">WPP software tracing</a> session. 


## -syntax


````
ULONGLONG WdfWmiProviderGetTracingHandle(
  _In_ WDFWMIPROVIDER WmiProvider
);
````


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object that the driver obtained by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> or <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>.


## -returns



<b>WdfWmiProviderGetTracingHandle</b> returns a handle to the event tracing logger.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If a driver sets the <b>WdfWmiProviderTracing</b> flag in the <b>Flags</b> member of the WMI provider object's <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure, it can call <b>WdfWmiProviderGetTracingHandle</b> to obtain a tracing handle after a provider instance has been registered. The driver can use the tracing handle as input to the <a href="..\wdm\nf-wdm-wmitracemessage.md">WmiTraceMessage</a> routine.

For more information about the <b>WdfWmiProviderGetTracingHandle</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting WMI Event Tracing</a>. For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example obtains a handle to a WPP tracing session's event logger.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONGLONG tracingHandle;

tracingHandle = WdfWmiProviderGetTracingHandle(wmiProvider);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>



 

 


