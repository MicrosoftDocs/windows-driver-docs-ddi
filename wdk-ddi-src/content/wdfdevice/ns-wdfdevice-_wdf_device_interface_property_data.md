---
UID: NS:wdfdevice._WDF_DEVICE_INTERFACE_PROPERTY_DATA
title: "_WDF_DEVICE_INTERFACE_PROPERTY_DATA"
author: windows-driver-content
description: The WDF_DEVICE_INTERFACE_PROPERTY_DATA structure describes a device interface property.
old-location: wdf\wdf_device_interface_property_data.htm
tech.root: wdf
ms.assetid: 2AC9E23B-928E-480F-A208-5A2DE92AEF4B
ms.date: 02/26/2018
ms.keywords: "*PWDF_DEVICE_INTERFACE_PROPERTY_DATA, PWDF_DEVICE_INTERFACE_PROPERTY_DATA, PWDF_DEVICE_INTERFACE_PROPERTY_DATA structure pointer, WDF_DEVICE_INTERFACE_PROPERTY_DATA, WDF_DEVICE_INTERFACE_PROPERTY_DATA structure, _WDF_DEVICE_INTERFACE_PROPERTY_DATA, wdf.wdf_device_interface_property_data, wdfdevice/PWDF_DEVICE_INTERFACE_PROPERTY_DATA, wdfdevice/WDF_DEVICE_INTERFACE_PROPERTY_DATA"
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_INTERFACE_PROPERTY_DATA
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_INTERFACE_PROPERTY_DATA, *PWDF_DEVICE_INTERFACE_PROPERTY_DATA
---

# _WDF_DEVICE_INTERFACE_PROPERTY_DATA structure


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b> structure describes a device interface property.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field InterfaceClassGUID

A pointer to a GUID that identifies the device interface class.


### -field ReferenceString

A pointer to a <b>UNICODE_STRING</b> structure that describes a reference
    string for the device interface. This parameter is optional and can
    be NULL.


### -field PropertyKey

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device 
    property key.


### -field Lcid

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -field Flags

Not currently used. Set this member to zero.


## -remarks



The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b> structure is used as input to the following methods:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265598">WdfDeviceAllocAndQueryInterfaceProperty</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265600">WdfDeviceAssignInterfaceProperty</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265607">WdfDeviceQueryInterfaceProperty</a>
</li>
</ul>
Drivers should initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn265630">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>.


#### Examples

For an example of how to use <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265600">WdfDeviceAssignInterfaceProperty</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265630">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265598">WdfDeviceAllocAndQueryInterfaceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265600">WdfDeviceAssignInterfaceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265607">WdfDeviceQueryInterfaceProperty</a>
 

 

