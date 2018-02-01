---
UID: NS:wdfwmi._WDF_WMI_INSTANCE_CONFIG
title: "_WDF_WMI_INSTANCE_CONFIG"
author: windows-driver-content
description: The WDF_WMI_INSTANCE_CONFIG structure contains configuration information for an instance of a WMI data provider.
old-location: wdf\wdf_wmi_instance_config.htm
old-project: wdf
ms.assetid: b2b2fd0c-c331-4132-b037-05c816626563
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFWMIRef_20be4139-3dcc-425e-9aaf-2851ceb794fb.xml, kmdf.wdf_wmi_instance_config, PWDF_WMI_INSTANCE_CONFIG structure pointer, WDF_WMI_INSTANCE_CONFIG structure, WDF_WMI_INSTANCE_CONFIG, wdfwmi/PWDF_WMI_INSTANCE_CONFIG, PWDF_WMI_INSTANCE_CONFIG, _WDF_WMI_INSTANCE_CONFIG, *PWDF_WMI_INSTANCE_CONFIG, wdf.wdf_wmi_instance_config, wdfwmi/WDF_WMI_INSTANCE_CONFIG
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfwmi.h
apiname:
-	WDF_WMI_INSTANCE_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_WMI_INSTANCE_CONFIG, *PWDF_WMI_INSTANCE_CONFIG
req.product: Windows 10 or later.
---

# _WDF_WMI_INSTANCE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_INSTANCE_CONFIG</b> structure contains configuration information for an instance of a WMI data provider.


## -syntax


````
typedef struct _WDF_WMI_INSTANCE_CONFIG {
  ULONG                               Size;
  WDFWMIPROVIDER                      Provider;
  PWDF_WMI_PROVIDER_CONFIG            ProviderConfig;
  BOOLEAN                             UseContextForQuery;
  BOOLEAN                             Register;
  PFN_WDF_WMI_INSTANCE_QUERY_INSTANCE EvtWmiInstanceQueryInstance;
  PFN_WDF_WMI_INSTANCE_SET_INSTANCE   EvtWmiInstanceSetInstance;
  PFN_WDF_WMI_INSTANCE_SET_ITEM       EvtWmiInstanceSetItem;
  PFN_WDF_WMI_INSTANCE_EXECUTE_METHOD EvtWmiInstanceExecuteMethod;
} WDF_WMI_INSTANCE_CONFIG, *PWDF_WMI_INSTANCE_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Provider

A handle to a WMI provider object that a driver obtained by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>. If this member is <b>NULL</b>, the <b>ProviderConfig</b> member must not be <b>NULL</b>.


### -field ProviderConfig

A pointer to a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure. If this member is <b>NULL</b>, the <b>Provider</b> member must not be <b>NULL</b>.


### -field UseContextForQuery

A Boolean value that, if <b>TRUE</b>, indicates that the driver will store instance data in the WMI instance object's context space and will not provide an <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a> callback function. Instead, the framework will service a WMI client's request for instance data by sending the contents of the context space to WMI. If this member is <b>FALSE</b>, the driver must provide an <i>EvtWmiInstanceQueryInstance</i> callback function (unless the instance data is write-only).

If <b>UseContextForQuery</b> is <b>TRUE</b>, the instance data must be read-only and therefore the driver cannot provide <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a> or <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a> callback functions.


### -field Register

A Boolean value that, if <b>TRUE</b>, indicates that the framework will register the provider instance with the system's WMI service after it creates a WMI instance object. If this member is <b>FALSE</b>, the driver must call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstanceregister.md">WdfWmiInstanceRegister</a> to register the provider instance. 


### -field EvtWmiInstanceQueryInstance

A pointer to the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceSetInstance

A pointer to the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceSetItem

A pointer to the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a> callback function for the provider instance, or <b>NULL</b>.


### -field EvtWmiInstanceExecuteMethod

A pointer to the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a> callback function for the provider instance, or <b>NULL</b>.


## -remarks


The <b>WDF_WMI_INSTANCE_CONFIG</b> structure is used as input to the <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a> method.

To initialize a <b>WDF_WMI_INSTANCE_CONFIG</b> structure, your driver should call <a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a> or <a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider_config.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>.



## -see-also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>

<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider_config.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstanceregister.md">WdfWmiInstanceRegister</a>

<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_INSTANCE_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

