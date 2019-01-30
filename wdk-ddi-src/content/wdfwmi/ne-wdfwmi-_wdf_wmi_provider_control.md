---
UID: NE:wdfwmi._WDF_WMI_PROVIDER_CONTROL
title: "_WDF_WMI_PROVIDER_CONTROL" (wdfwmi.h)
description: The WDF_WMI_PROVIDER_CONTROL enumeration defines the type of control functions that a WMI data provider can support.
old-location: wdf\wdf_wmi_provider_control.htm
tech.root: wdf
ms.assetid: c545b0a6-bb36-47a7-b55c-ee7eed5ade3a
ms.date: 02/26/2018
ms.keywords: DFWMIRef_a78e583c-59b7-4af3-a07f-8b774916f664.xml, WDF_WMI_PROVIDER_CONTROL, WDF_WMI_PROVIDER_CONTROL enumeration, WdfWmiControlInvalid, WdfWmiEventControl, WdfWmiInstanceControl, _WDF_WMI_PROVIDER_CONTROL, kmdf.wdf_wmi_provider_control, wdf.wdf_wmi_provider_control, wdfwmi/WDF_WMI_PROVIDER_CONTROL, wdfwmi/WdfWmiControlInvalid, wdfwmi/WdfWmiEventControl, wdfwmi/WdfWmiInstanceControl
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
-	WDF_WMI_PROVIDER_CONTROL
product:
- Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_CONTROL
---

# _WDF_WMI_PROVIDER_CONTROL enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_PROVIDER_CONTROL</b> enumeration defines the type of control functions that a WMI data provider can support.


## -enum-fields




### -field WdfWmiControlInvalid

For internal use only.


### -field WdfWmiEventControl

The driver must enable or disable delivering events for a provider instance.


### -field WdfWmiInstanceControl

The driver must enable or disable collecting data for a provider instance.


## -remarks



The <b>WDF_WMI_PROVIDER_CONTROL</b> enumeration is used as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a> method and the driver's <a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a> callback function.




## -see-also




<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a>
 

 

