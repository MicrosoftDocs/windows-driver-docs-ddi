---
UID: NS:wdfdevice._WDF_DEVICE_PROPERTY_DATA
title: _WDF_DEVICE_PROPERTY_DATA (wdfdevice.h)
description: The WDF_DEVICE_PROPERTY_DATA structure describes a device property.
old-location: wdf\wdf_device_property_data.htm
tech.root: wdf
ms.assetid: C49562C0-D8B6-4BAE-96EB-4005D9EB19DE
ms.date: 02/26/2018
keywords: ["_WDF_DEVICE_PROPERTY_DATA structure"]
ms.keywords: "*PWDF_DEVICE_PROPERTY_DATA, PWDF_DEVICE_PROPERTY_DATA, PWDF_DEVICE_PROPERTY_DATA structure pointer, WDF_DEVICE_PROPERTY_DATA, WDF_DEVICE_PROPERTY_DATA structure, _WDF_DEVICE_PROPERTY_DATA, wdf.wdf_device_property_data, wdfdevice/PWDF_DEVICE_PROPERTY_DATA, wdfdevice/WDF_DEVICE_PROPERTY_DATA"
f1_keywords:
 - "wdfdevice/WDF_DEVICE_PROPERTY_DATA"
 - "WDF_DEVICE_PROPERTY_DATA"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_PROPERTY_DATA
targetos: Windows
req.typenames: WDF_DEVICE_PROPERTY_DATA, *PWDF_DEVICE_PROPERTY_DATA
---

# _WDF_DEVICE_PROPERTY_DATA structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_PROPERTY_DATA</b> structure describes a device property.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field PropertyKey

A pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> structure that specifies the device 
    property key.


### -field Lcid

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/63d3d639-7fd2-4afb-abbe-0d5b5551eef8">LCID Structure</a>.


### -field Flags

Set to  <b>PLUGPLAY_PROPERTY_PERSISTENT</b> if this property value is being set by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignproperty">WdfDeviceAssignProperty</a>. Otherwise, set this member to zero.


## -remarks



The <b>WDF_DEVICE_PROPERTY_DATA</b> structure is used as input to the following methods:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignproperty">WdfDeviceAssignProperty</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitquerypropertyex">WdfFdoInitQueryPropertyEx</a>
</li>
</ul>
Drivers should initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_property_data_init">WDF_DEVICE_PROPERTY_DATA_INIT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_property_data_init">WDF_DEVICE_PROPERTY_DATA_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignproperty">WdfDeviceAssignProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitquerypropertyex">WdfFdoInitQueryPropertyEx</a>
 

 

