---
UID: NS:wdfwmi._WDF_WMI_PROVIDER_CONFIG
title: "_WDF_WMI_PROVIDER_CONFIG"
author: windows-driver-content
description: The WDF_WMI_PROVIDER_CONFIG structure contains configuration information for a driver's WMI data block.
old-location: wdf\wdf_wmi_provider_config.htm
old-project: wdf
ms.assetid: 91b8e4e8-f144-4469-bedf-18f40be7e649
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_WMI_PROVIDER_CONFIG, DFWMIRef_6cf9c574-aa7a-4184-97c7-bd2b2134f5ac.xml, PWDF_WMI_PROVIDER_CONFIG, PWDF_WMI_PROVIDER_CONFIG structure pointer, WDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG structure, _WDF_WMI_PROVIDER_CONFIG, kmdf.wdf_wmi_provider_config, wdf.wdf_wmi_provider_config, wdfwmi/PWDF_WMI_PROVIDER_CONFIG, wdfwmi/WDF_WMI_PROVIDER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfwmi.h
api_name:
-	WDF_WMI_PROVIDER_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_CONFIG, *PWDF_WMI_PROVIDER_CONFIG
req.product: Windows 10 or later.
---

# _WDF_WMI_PROVIDER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_PROVIDER_CONFIG</b> structure contains configuration information for a driver's WMI data block.


## -syntax


````
typedef struct _WDF_WMI_PROVIDER_CONFIG {
  ULONG                                 Size;
  GUID                                  Guid;
  ULONG                                 Flags;
  ULONG                                 MinInstanceBufferSize;
  PFN_WDF_WMI_PROVIDER_FUNCTION_CONTROL EvtWmiProviderFunctionControl;
} WDF_WMI_PROVIDER_CONFIG, *PWDF_WMI_PROVIDER_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Guid

The symbolic name of a <a href="https://msdn.microsoft.com/library/windows/hardware/dn922935">GUID</a> that identifies a WMI data block.


### -field Flags

A bitwise OR of <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_flags.md">WDF_WMI_PROVIDER_FLAGS</a>-typed values. 


### -field MinInstanceBufferSize

The minimum size, in bytes, of fixed-length buffers that the <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a> and <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a> callback functions will use for provider instances. This member must be zero for variable-length buffers. This member is ignored if <b>WdfWmiProviderEventOnly</b> is set in the <b>Flags</b> member.


### -field EvtWmiProviderFunctionControl

A pointer to the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function, or <b>NULL</b>.


## -remarks



The <b>WDF_WMI_PROVIDER_CONFIG</b> structure is used as input to the <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> method.

To initialize a <b>WDF_WMI_PROVIDER_CONFIG</b> structure, your driver should call <a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_provider_config_init.md">WDF_WMI_PROVIDER_CONFIG_INIT</a>.




## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_provider_config_init.md">WDF_WMI_PROVIDER_CONFIG_INIT</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>



<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_flags.md">WDF_WMI_PROVIDER_FLAGS</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>



 

 


