---
UID: NE:wdfwmi._WDF_WMI_PROVIDER_FLAGS
title: "_WDF_WMI_PROVIDER_FLAGS"
author: windows-driver-content
description: The WDF_WMI_PROVIDER_FLAGS enumeration defines configuration flags for a driver's WMI data provider.
old-location: wdf\wdf_wmi_provider_flags.htm
tech.root: wdf
ms.assetid: 85b1a4b4-53e0-4663-b813-18801f8b639b
ms.date: 02/26/2018
ms.keywords: DFWMIRef_e093a379-bdc9-4b69-90e8-294b9d55eeea.xml, WDF_WMI_PROVIDER_FLAGS, WDF_WMI_PROVIDER_FLAGS enumeration, WdfWmiProviderEventOnly, WdfWmiProviderExpensive, WdfWmiProviderTracing, WdfWmiProviderValidFlags, _WDF_WMI_PROVIDER_FLAGS, kmdf.wdf_wmi_provider_flags, wdf.wdf_wmi_provider_flags, wdfwmi/WDF_WMI_PROVIDER_FLAGS, wdfwmi/WdfWmiProviderEventOnly, wdfwmi/WdfWmiProviderExpensive, wdfwmi/WdfWmiProviderTracing, wdfwmi/WdfWmiProviderValidFlags
ms.topic: enum
req.header: wdfwmi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfwmi.h
api_name:
-	WDF_WMI_PROVIDER_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
---

# _WDF_WMI_PROVIDER_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration defines configuration flags for a driver's WMI data provider.


## -enum-fields




### -field WdfWmiProviderEventOnly

WMI clients can receive notification of WMI events, but they cannot query or set instance data. The driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551182">WdfWmiInstanceFireEvent</a>, but it does not provide any instance-specific callback functions.


### -field WdfWmiProviderExpensive

Collecting the provider's data can potentially affect the driver's performance, so the driver will not collect data unless a WMI client has registered to use it. The framework calls the driver's <a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a> callback function, passing the <b>WdfWmiInstanceControl</b> value (from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553078">WDF_WMI_PROVIDER_CONTROL</a> enumeration), to inform the driver to begin collecting data. If the driver does not provide an <i>EvtWmiProviderFunctionControl</i> callback function, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a>.


### -field WdfWmiProviderTracing

The WMI data provider supports WMI event tracing. The driver can obtain the tracing handle by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551198">WdfWmiProviderGetTracingHandle</a>. If this flag is set, no other flags can be set.


### -field WdfWmiProviderValidFlags

The bitwise OR of all flags. Drivers should not use this value.


## -remarks



The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://msdn.microsoft.com/c545b0a6-bb36-47a7-b55c-ee7eed5ade3a">WdfWmiInstanceControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551182">WdfWmiInstanceFireEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551198">WdfWmiProviderGetTracingHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a>
 

 

