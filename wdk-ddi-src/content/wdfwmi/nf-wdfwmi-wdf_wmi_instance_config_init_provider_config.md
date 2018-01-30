---
UID: NF:wdfwmi.WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
title: WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function
author: windows-driver-content
description: The WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function initializes a WDF_WMI_INSTANCE_CONFIG structure and stores a pointer to a specified WDF_WMI_PROVIDER_CONFIG structure.
old-location: wdf\wdf_wmi_instance_config_init_provider_config.htm
old-project: wdf
ms.assetid: e65a7fa3-1c9c-447a-b99a-a63570c9e233
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function, wdf.wdf_wmi_instance_config_init_provider_config, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG, DFWMIRef_6aec4b1b-494c-4f9f-89c3-a8e79fa552da.xml, kmdf.wdf_wmi_instance_config_init_provider_config, wdfwmi/WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
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
-	WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> function initializes a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure and stores a pointer to a specified <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure.


## -syntax


````
VOID WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG(
  _Out_ PWDF_WMI_INSTANCE_CONFIG Config,
  _In_  PWDF_WMI_PROVIDER_CONFIG ProviderConfig
);
````


## -parameters




### -param Config [out]

A pointer to a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure.


### -param ProviderConfig [in]

A pointer to a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure.


## -returns


None



## -remarks


The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> function zeros the specified <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure and sets its <b>Size</b> member. The function also sets the structure's <b>ProviderConfig</b> member to the specified pointer.

Your driver should call <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> to initialize a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure if it does not call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.



## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>

<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

