---
UID: NF:wdfwmi.WdfWmiProviderCreate
title: WdfWmiProviderCreate function (wdfwmi.h)
description: The WdfWmiProviderCreate method creates a WMI provider object that represents a WMI data block.
old-location: wdf\wdfwmiprovidercreate.htm
tech.root: wdf
ms.assetid: 07aed86f-870e-431b-b1bb-403395c35946
ms.date: 02/26/2018
ms.keywords: DFWMIRef_f1b26bb3-d191-4f2b-9289-c76ef93769b5.xml, WdfWmiProviderCreate, WdfWmiProviderCreate method, kmdf.wdfwmiprovidercreate, wdf.wdfwmiprovidercreate, wdfwmi/WdfWmiProviderCreate
f1_keywords:
 - "wdfwmi/WdfWmiProviderCreate"
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
- WdfWmiProviderCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWmiProviderCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiProviderCreate</b> method creates a WMI provider object that represents a WMI data block.


## -parameters




### -param Device [in]

A handle to a framework device object that will be the new provider object's parent object. The device object cannot be a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-control-device-objects">control device object</a>.


### -param WmiProviderConfig [in]

A pointer to a caller-initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure that contains configuration information about the WMI data block.


### -param ProviderAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the new WMI provider object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param WmiProvider [out]

A pointer to a location that receives a handle to the new WMI provider object.


## -returns



<b>WdfWmiProviderCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure that the <i>WmiProviderConfig</i> parameter pointed to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The driver has already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> for the specified device and WMI data block.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfWmiProviderCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver must call <b>WdfWmiProviderCreate</b> to create a WMI provider object if the driver will create multiple instances of the provider. If the driver will create only one instance of the provider, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a> without first calling <b>WdfWmiProviderCreate</b>. 

A driver can call <b>WdfWmiProviderCreate</b> at any time, but drivers typically call <b>WdfWmiProviderCreate</b> from within their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback functions. 

The parent of each WMI provider object is the device's framework device object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

After a driver calls <b>WdfWmiProviderCreate</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidergetdevice">WdfWmiProviderGetDevice</a> to retrieve a handle to the provider object's parent device object.

After a driver creates a WMI provider object, the driver cannot delete the object. The framework deletes a device's WMI provider objects when it deletes the framework device object that represents the device. WMI provider objects use minimal system resources.

For more information about the <b>WdfWmiProviderCreate</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure and calls <b>WdfWmiProviderCreate</b>.

```cpp
WDF_WMI_PROVIDER_CONFIG config;
WDFWMIPROVIDER provider;
GUID providerGuid = MY_WMI_DATA_BLOCK_GUID;
NTSTATUS status;

WDF_WMI_PROVIDER_CONFIG_INIT(
                             &config,
                             providerGuid
                             );
config.Flags = WdfWmiProviderTracing;
config.EvtWmiProviderFunctionControl = MyProviderFunctionControl;

status = WdfWmiProviderCreate(
                              Device,
                              &config,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &provider
                              );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidergetdevice">WdfWmiProviderGetDevice</a>
 

 

