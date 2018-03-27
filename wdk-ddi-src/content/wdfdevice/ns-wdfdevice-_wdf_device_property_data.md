---
UID: NS:wdfdevice._WDF_DEVICE_PROPERTY_DATA
title: "_WDF_DEVICE_PROPERTY_DATA"
author: windows-driver-content
description: The WDF_DEVICE_PROPERTY_DATA structure describes a device property.
old-location: wdf\wdf_device_property_data.htm
old-project: wdf
ms.assetid: C49562C0-D8B6-4BAE-96EB-4005D9EB19DE
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_DEVICE_PROPERTY_DATA, PWDF_DEVICE_PROPERTY_DATA, PWDF_DEVICE_PROPERTY_DATA structure pointer, WDF_DEVICE_PROPERTY_DATA, WDF_DEVICE_PROPERTY_DATA structure, _WDF_DEVICE_PROPERTY_DATA, wdf.wdf_device_property_data, wdfdevice/PWDF_DEVICE_PROPERTY_DATA, wdfdevice/WDF_DEVICE_PROPERTY_DATA"
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
-	WDF_DEVICE_PROPERTY_DATA
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_PROPERTY_DATA, *PWDF_DEVICE_PROPERTY_DATA
req.product: Windows 10 or later.
---

# _WDF_DEVICE_PROPERTY_DATA structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PROPERTY_DATA</b> structure describes a device property.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field PropertyKey

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device 
    property key.


### -field Lcid

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -field Flags

Set to  <b>PLUGPLAY_PROPERTY_PERSISTENT</b> if this property value is being set by <a href="https://msdn.microsoft.com/library/windows/hardware/dn265601">WdfDeviceAssignProperty</a>. Otherwise, set this member to zero.


## -remarks



The <b>WDF_DEVICE_PROPERTY_DATA</b> structure is used as input to the following methods:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265601">WdfDeviceAssignProperty</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265608">WdfDeviceQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265612">WdfFdoInitAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265613">WdfFdoInitQueryPropertyEx</a>
</li>
</ul>
Drivers should initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn265633">WDF_DEVICE_PROPERTY_DATA_INIT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265633">WDF_DEVICE_PROPERTY_DATA_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265601">WdfDeviceAssignProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265608">WdfDeviceQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265612">WdfFdoInitAllocAndQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265613">WdfFdoInitQueryPropertyEx</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PROPERTY_DATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

