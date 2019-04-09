---
UID: NS:wdfwmi._WDF_WMI_INSTANCE_CONFIG
title: _WDF_WMI_INSTANCE_CONFIG (wdfwmi.h)
description: The WDF_WMI_INSTANCE_CONFIG structure contains configuration information for an instance of a WMI data provider.
old-location: wdf\wdf_wmi_instance_config.htm
tech.root: wdf
ms.assetid: b2b2fd0c-c331-4132-b037-05c816626563
ms.date: 02/26/2018
ms.keywords: "*PWDF_WMI_INSTANCE_CONFIG, DFWMIRef_20be4139-3dcc-425e-9aaf-2851ceb794fb.xml, PWDF_WMI_INSTANCE_CONFIG, PWDF_WMI_INSTANCE_CONFIG structure pointer, WDF_WMI_INSTANCE_CONFIG, WDF_WMI_INSTANCE_CONFIG structure, _WDF_WMI_INSTANCE_CONFIG, kmdf.wdf_wmi_instance_config, wdf.wdf_wmi_instance_config, wdfwmi/PWDF_WMI_INSTANCE_CONFIG, wdfwmi/WDF_WMI_INSTANCE_CONFIG"
ms.topic: struct
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfwmi.h
api_name:
- WDF_WMI_INSTANCE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_WMI_INSTANCE_CONFIG, *PWDF_WMI_INSTANCE_CONFIG
---

# _WDF_WMI_INSTANCE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_INSTANCE_CONFIG</b> structure contains configuration information for an instance of a WMI data provider.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Provider

A handle to a WMI provider object that a driver obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>. If this member is <b>NULL</b>, the <b>ProviderConfig</b> member must not be <b>NULL</b>.


### -field ProviderConfig

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure. If this member is <b>NULL</b>, the <b>Provider</b> member must not be <b>NULL</b>.


### -field UseContextForQuery

A Boolean value that, if <b>TRUE</b>, indicates that the driver will store instance data in the WMI instance object's context space and will not provide an <a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a> callback function. Instead, the framework will service a WMI client's request for instance data by sending the contents of the context space to WMI. If this member is <b>FALSE</b>, the driver must provide an <i>EvtWmiInstanceQueryInstance</i> callback function (unless the instance data is write-only).

If <b>UseContextForQuery</b> is <b>TRUE</b>, the instance data must be read-only and therefore the driver cannot provide <a href="https://msdn.microsoft.com/defd33c5-90ae-40c9-9123-7c3de2c77f35">EvtWmiInstanceSetInstance</a> or <a href="https://msdn.microsoft.com/3011d92c-b12b-4240-8a4e-aa039ab8e053">EvtWmiInstanceSetItem</a> callback functions.


### -field Register

A Boolean value that, if <b>TRUE</b>, indicates that the framework will register the provider instance with the system's WMI service after it creates a WMI instance object. If this member is <b>FALSE</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551190">WdfWmiInstanceRegister</a> to register the provider instance. 


### -field EvtWmiInstanceQueryInstance

A pointer to the driver's <a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceSetInstance

A pointer to the driver's <a href="https://msdn.microsoft.com/defd33c5-90ae-40c9-9123-7c3de2c77f35">EvtWmiInstanceSetInstance</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceSetItem

A pointer to the driver's <a href="https://msdn.microsoft.com/3011d92c-b12b-4240-8a4e-aa039ab8e053">EvtWmiInstanceSetItem</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceExecuteMethod

A pointer to the driver's <a href="https://msdn.microsoft.com/b14de1d7-0df2-46d1-a3bd-c23f33d3ed75">EvtWmiInstanceExecuteMethod</a> callback function for the provider instance, or <b>NULL</b>.


## -remarks



The <b>WDF_WMI_INSTANCE_CONFIG</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a> method.

To initialize a <b>WDF_WMI_INSTANCE_CONFIG</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553061">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553063">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>.




## -see-also




<a href="https://msdn.microsoft.com/b14de1d7-0df2-46d1-a3bd-c23f33d3ed75">EvtWmiInstanceExecuteMethod</a>



<a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a>



<a href="https://msdn.microsoft.com/defd33c5-90ae-40c9-9123-7c3de2c77f35">EvtWmiInstanceSetInstance</a>



<a href="https://msdn.microsoft.com/3011d92c-b12b-4240-8a4e-aa039ab8e053">EvtWmiInstanceSetItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553061">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553063">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551190">WdfWmiInstanceRegister</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>
 

 

