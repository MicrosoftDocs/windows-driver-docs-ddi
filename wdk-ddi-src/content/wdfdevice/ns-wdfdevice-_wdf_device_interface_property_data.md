---
UID: NS:wdfdevice._WDF_DEVICE_INTERFACE_PROPERTY_DATA
title: "_WDF_DEVICE_INTERFACE_PROPERTY_DATA"
author: windows-driver-content
description: The WDF_DEVICE_INTERFACE_PROPERTY_DATA structure describes a device interface property.
old-location: wdf\wdf_device_interface_property_data.htm
old-project: wdf
ms.assetid: 2AC9E23B-928E-480F-A208-5A2DE92AEF4B
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWDF_DEVICE_INTERFACE_PROPERTY_DATA, PWDF_DEVICE_INTERFACE_PROPERTY_DATA, PWDF_DEVICE_INTERFACE_PROPERTY_DATA structure pointer, WDF_DEVICE_INTERFACE_PROPERTY_DATA, WDF_DEVICE_INTERFACE_PROPERTY_DATA structure, _WDF_DEVICE_INTERFACE_PROPERTY_DATA, wdf.wdf_device_interface_property_data, wdfdevice/PWDF_DEVICE_INTERFACE_PROPERTY_DATA, wdfdevice/WDF_DEVICE_INTERFACE_PROPERTY_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_DEVICE_INTERFACE_PROPERTY_DATA
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_INTERFACE_PROPERTY_DATA, *PWDF_DEVICE_INTERFACE_PROPERTY_DATA
req.product: Windows 10 or later.
---

# _WDF_DEVICE_INTERFACE_PROPERTY_DATA structure


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b> structure describes a device interface property.


## -syntax


````
typedef struct _WDF_DEVICE_INTERFACE_PROPERTY_DATA {
  ULONG            Size;
  const GUID       *InterfaceClassGUID;
  PCUNICODE_STRING ReferenceString;
  const DEVPROPKEY *PropertyKey;
  LCID             Lcid;
  ULONG            Flags;
} WDF_DEVICE_INTERFACE_PROPERTY_DATA, *PWDF_DEVICE_INTERFACE_PROPERTY_DATA;
````


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

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -field Flags

Not currently used. Set this member to zero.


## -remarks



The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b> structure is used as input to the following methods:

<ul>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md">WdfDeviceAllocAndQueryInterfaceProperty</a>
</li>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>
</li>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryinterfaceproperty.md">WdfDeviceQueryInterfaceProperty</a>
</li>
</ul>
Drivers should initialize this structure by calling <a href="..\wdfdevice\nf-wdfdevice-wdf_device_interface_property_data_init.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>.


#### Examples

For an example of how to use <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdf_device_interface_property_data_init.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md">WdfDeviceAllocAndQueryInterfaceProperty</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryinterfaceproperty.md">WdfDeviceQueryInterfaceProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_INTERFACE_PROPERTY_DATA structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

