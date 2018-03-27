---
UID: NF:wdfwmi.WDF_WMI_PROVIDER_CONFIG_INIT
title: WDF_WMI_PROVIDER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_WMI_PROVIDER_CONFIG_INIT function initializes a WDF_WMI_PROVIDER_CONFIG structure.
old-location: wdf\wdf_wmi_provider_config_init.htm
old-project: wdf
ms.assetid: a63079ab-45ec-44b2-8769-f5b30f378972
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_34f9d195-3f6b-419d-bab7-29ad49c3d177.xml, WDF_WMI_PROVIDER_CONFIG_INIT, WDF_WMI_PROVIDER_CONFIG_INIT function, kmdf.wdf_wmi_provider_config_init, wdf.wdf_wmi_provider_config_init, wdfwmi/WDF_WMI_PROVIDER_CONFIG_INIT
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
-	WDF_WMI_PROVIDER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WDF_WMI_PROVIDER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_PROVIDER_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure.


### -param Guid [in]

A pointer to a GUID that identifies a WMI data provider's data block. 


## -returns



None




## -remarks



The <b>WDF_WMI_PROVIDER_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure and sets its <b>Size</b> member. This function also copies the specified GUID into the structure's <b>Guid</b> member.


#### Examples

For a code example that uses <b>WDF_WMI_PROVIDER_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_PROVIDER_CONFIG_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

