---
UID: NF:wdfwmi.WdfWmiInstanceRegister
title: WdfWmiInstanceRegister function
author: windows-driver-content
description: The WdfWmiInstanceRegister method registers a specified instance of a WMI data provider with the system's WMI service.
old-location: wdf\wdfwmiinstanceregister.htm
old-project: wdf
ms.assetid: 95f97b95-fdb1-43f2-b733-4054adda4c41
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFWMIINSTANCEREGISTER, WdfWmiInstanceRegister method, wdf.wdfwmiinstanceregister, WdfWmiInstanceRegister, wdfwmi/WdfWmiInstanceRegister, kmdf.wdfwmiinstanceregister, DFWMIRef_56a3eb85-855f-4ad9-ad81-c630fecf98b3.xml
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfWmiInstanceRegister
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceRegister function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceRegister</b> method registers a specified instance of a WMI data provider with the system's WMI service.


## -syntax


````
NTSTATUS WdfWmiInstanceRegister(
  _In_ WDFWMIINSTANCE WmiInstance
);
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


## -returns



<b>WdfWmiInstanceRegister</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The specified WMI instance has already been registered.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Provider instances are not available to WMI clients until they have been registered. Your driver must either call <b>WdfWmiInstanceRegister</b> or set the <b>Register</b> member of the instance's <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure to <b>TRUE</b>.

For more information about the <b>WdfWmiInstanceRegister</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/initializing-wmi-support-in-your-driver">Registering Provider Instances</a>. For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

<b>WdfWmiInstanceRegister</b> registers the provider instance synchronously (that is, before returning) if it is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL &gt; PASSIVE_LEVEL. 


#### Examples

The following code example registers a specified instance of a WMI data provider with the system's WMI service.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;

status = WdfWmiInstanceRegister(wmiInstance);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancederegister.md">WdfWmiInstanceDeregister</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceRegister method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

