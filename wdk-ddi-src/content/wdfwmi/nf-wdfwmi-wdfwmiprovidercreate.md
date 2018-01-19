---
UID: NF:wdfwmi.WdfWmiProviderCreate
title: WdfWmiProviderCreate function
author: windows-driver-content
description: The WdfWmiProviderCreate method creates a WMI provider object that represents a WMI data block.
old-location: wdf\wdfwmiprovidercreate.htm
old-project: wdf
ms.assetid: 07aed86f-870e-431b-b1bb-403395c35946
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfWmiProviderCreate
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
req.alt-api: WdfWmiProviderCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
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
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiProviderCreate function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiProviderCreate</b> method creates a WMI provider object that represents a WMI data block.



## -syntax

````
NTSTATUS WdfWmiProviderCreate(
  _In_     WDFDEVICE                Device,
  _In_     PWDF_WMI_PROVIDER_CONFIG WmiProviderConfig,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES   ProviderAttributes,
  _Out_    WDFWMIPROVIDER           *WmiProvider
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that will be the new provider object's parent object. The device object cannot be a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">control device object</a>.


### -param WmiProviderConfig [in]

A pointer to a caller-initialized <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure that contains configuration information about the WMI data block.


### -param ProviderAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the new WMI provider object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param WmiProvider [out]

A pointer to a location that receives a handle to the new WMI provider object.


## -returns
<b>WdfWmiProviderCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure that the <i>WmiProviderConfig</i> parameter pointed to was incorrect.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory to complete the operation.
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>The driver has already called <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> for the specified device and WMI data block.

 

For a list of other return values that the <b>WdfWmiProviderCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Your driver must call <b>WdfWmiProviderCreate</b> to create a WMI provider object if the driver will create multiple instances of the provider. If the driver will create only one instance of the provider, it can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a> without first calling <b>WdfWmiProviderCreate</b>. 

A driver can call <b>WdfWmiProviderCreate</b> at any time, but drivers typically call <b>WdfWmiProviderCreate</b> from within their <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback functions. 

The parent of each WMI provider object is the device's framework device object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

After a driver calls <b>WdfWmiProviderCreate</b>, the driver can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergetdevice.md">WdfWmiProviderGetDevice</a> to retrieve a handle to the provider object's parent device object.

After a driver creates a WMI provider object, the driver cannot delete the object. The framework deletes a device's WMI provider objects when it deletes the framework device object that represents the device. WMI provider objects use minimal system resources.

For more information about the <b>WdfWmiProviderCreate</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

The following code example initializes a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure and calls <b>WdfWmiProviderCreate</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergetdevice.md">WdfWmiProviderGetDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiProviderCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

