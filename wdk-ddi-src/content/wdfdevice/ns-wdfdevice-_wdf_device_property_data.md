---
UID: NS:wdfdevice._WDF_DEVICE_PROPERTY_DATA
title: _WDF_DEVICE_PROPERTY_DATA
author: windows-driver-content
description: The WDF_DEVICE_PROPERTY_DATA structure describes a device property.
old-location: wdf\wdf_device_property_data.htm
old-project: wdf
ms.assetid: C49562C0-D8B6-4BAE-96EB-4005D9EB19DE
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_DEVICE_PROPERTY_DATA, WDF_DEVICE_PROPERTY_DATA, *PWDF_DEVICE_PROPERTY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: WDF_DEVICE_PROPERTY_DATA
req.alt-loc: wdfdevice.h
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
req.typenames: WDF_DEVICE_PROPERTY_DATA, *PWDF_DEVICE_PROPERTY_DATA
req.product: Windows 10 or later.
---

# _WDF_DEVICE_PROPERTY_DATA structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PROPERTY_DATA</b> structure describes a device property.



## -syntax

````
typedef struct _WDF_DEVICE_PROPERTY_DATA {
  ULONG            Size;
  const DEVPROPKEY *PropertyKey;
  LCID             Lcid;
  ULONG            Flags;
} WDF_DEVICE_PROPERTY_DATA, *PWDF_DEVICE_PROPERTY_DATA;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field PropertyKey

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device 
    property key.


### -field Lcid

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -field Flags

Set to  <b>PLUGPLAY_PROPERTY_PERSISTENT</b> if this property value is being set by <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignproperty.md">WdfDeviceAssignProperty</a>. Otherwise, set this member to zero.


## -remarks
The <b>WDF_DEVICE_PROPERTY_DATA</b> structure is used as input to the following methods:

Drivers should initialize this structure by calling <a href="..\wdfdevice\nf-wdfdevice-wdf_device_property_data_init.md">WDF_DEVICE_PROPERTY_DATA_INIT</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdf_device_property_data_init.md">WDF_DEVICE_PROPERTY_DATA_INIT</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandquerypropertyex.md">WdfDeviceAllocAndQueryPropertyEx</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignproperty.md">WdfDeviceAssignProperty</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequerypropertyex.md">WdfDeviceQueryPropertyEx</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandquerypropertyex.md">WdfFdoInitAllocAndQueryPropertyEx</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitquerypropertyex.md">WdfFdoInitQueryPropertyEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PROPERTY_DATA structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

