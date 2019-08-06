---
UID: NF:wdfwmi.WdfWmiProviderIsEnabled
title: WdfWmiProviderIsEnabled function (wdfwmi.h)
description: The WdfWmiProviderIsEnabled method determines if either data collection or event notification is enabled for a specified WMI data provider.
old-location: wdf\wdfwmiproviderisenabled.htm
tech.root: wdf
ms.assetid: 7b4fd9ff-09a7-44df-a3e6-0af5d7ea624e
ms.date: 02/26/2018
ms.keywords: DFWMIRef_3231e5bd-aa1c-4bf8-92ef-4b6c29308d95.xml, WdfWmiProviderIsEnabled, WdfWmiProviderIsEnabled method, kmdf.wdfwmiproviderisenabled, wdf.wdfwmiproviderisenabled, wdfwmi/WdfWmiProviderIsEnabled
ms.topic: function
f1_keywords:
 - "wdfwmi/WdfWmiProviderIsEnabled"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfWmiProviderIsEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWmiProviderIsEnabled function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiProviderIsEnabled</b> method determines if either data collection or event notification is enabled for a specified WMI data provider.


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object that the driver obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>.


### -param ProviderControl [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_control">WDF_WMI_PROVIDER_CONTROL</a>-typed value that specifies one of the types of control functions (data collection or event notification) that a WMI data provider can support.


## -returns



<b>WdfWmiProviderIsEnabled</b> returns <b>TRUE</b> if the capability that the <i>ProviderControl</i> parameter specifies is enabled and <b>FALSE</b> otherwise.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver that does not provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a> callback function can call <b>WdfWmiProviderIsEnabled</b> to determine if data collection or event notification is enabled.


#### Examples

The following code example determines if event notification is enabled for a specified WMI data provider.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN eventNotifEnabled;

eventNotifEnabled = WdfWmiProviderIsEnabled(
                                            wmiProvider,
                                            WdfWmiEventControl
                                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_control">WDF_WMI_PROVIDER_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>
 

 

