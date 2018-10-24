---
UID: NF:wdfwmi.WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
title: WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function
author: windows-driver-content
description: The WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function initializes a WDF_WMI_INSTANCE_CONFIG structure and stores a pointer to a specified WDF_WMI_PROVIDER_CONFIG structure.
old-location: wdf\wdf_wmi_instance_config_init_provider_config.htm
tech.root: wdf
ms.assetid: e65a7fa3-1c9c-447a-b99a-a63570c9e233
ms.date: 02/26/2018
ms.keywords: DFWMIRef_6aec4b1b-494c-4f9f-89c3-a8e79fa552da.xml, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function, kmdf.wdf_wmi_instance_config_init_provider_config, wdf.wdf_wmi_instance_config_init_provider_config, wdfwmi/WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
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
-	WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure and stores a pointer to a specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure.


### -param ProviderConfig [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure.


## -returns



None




## -remarks



The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure and sets its <b>Size</b> member. The function also sets the structure's <b>ProviderConfig</b> member to the specified pointer.

Your driver should call <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure if it does not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>.


#### Examples

For a code example the uses <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553061">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>
 

 

