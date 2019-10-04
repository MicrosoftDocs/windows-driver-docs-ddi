---
UID: NF:wdfwmi.WdfWmiInstanceRegister
title: WdfWmiInstanceRegister function (wdfwmi.h)
description: The WdfWmiInstanceRegister method registers a specified instance of a WMI data provider with the system's WMI service.
old-location: wdf\wdfwmiinstanceregister.htm
tech.root: wdf
ms.assetid: 95f97b95-fdb1-43f2-b733-4054adda4c41
ms.date: 02/26/2018
ms.keywords: DFWMIRef_56a3eb85-855f-4ad9-ad81-c630fecf98b3.xml, WdfWmiInstanceRegister, WdfWmiInstanceRegister method, kmdf.wdfwmiinstanceregister, wdf.wdfwmiinstanceregister, wdfwmi/WdfWmiInstanceRegister
ms.topic: function
f1_keywords:
 - "wdfwmi/WdfWmiInstanceRegister"
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
- WdfWmiInstanceRegister
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWmiInstanceRegister function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiInstanceRegister</b> method registers a specified instance of a WMI data provider with the system's WMI service.


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>.


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
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Provider instances are not available to WMI clients until they have been registered. Your driver must either call <b>WdfWmiInstanceRegister</b> or set the <b>Register</b> member of the instance's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure to <b>TRUE</b>.

For more information about the <b>WdfWmiInstanceRegister</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-wmi-support-in-your-driver">Registering Provider Instances</a>. For more information about WMI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

<b>WdfWmiInstanceRegister</b> registers the provider instance synchronously (that is, before returning) if it is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL > PASSIVE_LEVEL. 


#### Examples

The following code example registers a specified instance of a WMI data provider with the system's WMI service.

```cpp
NTSTATUS  status;

status = WdfWmiInstanceRegister(wmiInstance);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfwmi/nf-wdfwmi-wdfwmiinstancederegister">WdfWmiInstanceDeregister</a>
 

 

