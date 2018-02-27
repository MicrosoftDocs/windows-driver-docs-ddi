---
UID: NF:wdfwmi.WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
title: WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function
author: windows-driver-content
description: The WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function initializes a WDF_WMI_INSTANCE_CONFIG structure and stores a specified handle to a WMI provider object.
old-location: wdf\wdf_wmi_instance_config_init_provider.htm
old-project: wdf
ms.assetid: 6509fded-c244-4d86-9b20-23790ec58f4a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFWMIRef_beb80d61-7fcb-4234-97ef-41e917cd51f5.xml, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function, kmdf.wdf_wmi_instance_config_init_provider, wdf.wdf_wmi_instance_config_init_provider, wdfwmi/WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfwmi.h
api_name:
-	WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> function initializes a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure and stores a specified handle to a WMI provider object.


## -syntax


````
VOID WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER(
  _Out_ PWDF_WMI_INSTANCE_CONFIG Config,
  _In_  WDFWMIPROVIDER           Provider
);
````


## -parameters




### -param Config [out]

A pointer to a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure.


### -param Provider [in]

A handle to a WMI provider object that the driver obtained by a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>.


## -returns



None




## -remarks



The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> function zeros the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure that the <i>Config</i> parameter specifies and sets its <b>Size</b> member. This function also sets the structure's <b>Provider</b> member to the handle that the <i>Provider</i> parameter specifies.

Your driver should call <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> to initialize a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure if it calls <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


#### Examples

The following code example initializes a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure and calls <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>. Then, the example initializes a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure and calls <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_WMI_PROVIDER_CONFIG  providerConfig;
WDFWMIPROVIDER  provider;
GUID  providerGuid = MY_WMI_DATA_BLOCK_GUID;
WDF_WMI_INSTANCE_CONFIG  instanceConfig;
WDFWMIINSTANCE  instanceHandle;
NTSTATUS  status;

WDF_WMI_PROVIDER_CONFIG_INIT(
                             &amp;providerConfig,
                             providerGuid
                             );
providerConfig.Flags = WdfWmiProviderTracing;
providerConfig.EvtWmiProviderFunctionControl = MyProviderFunctionControl;

status = WdfWmiProviderCreate(
                              Device,
                              &amp;providerConfig,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &amp;provider
                              );

if (!NT_SUCCESS(status)) {
    return status;
}
WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER(
                                      &amp;instanceConfig,
                                      provider
                                      );
status = WdfWmiInstanceCreate(
                              Device,
                              &amp;instanceConfig,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &amp;instanceHandle
                              );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_provider_config_init.md">WDF_WMI_PROVIDER_CONFIG_INIT</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider_config.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

