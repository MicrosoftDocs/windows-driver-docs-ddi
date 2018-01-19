---
UID: NF:wdfpdo.WdfPdoInitAddDeviceText
title: WdfPdoInitAddDeviceText function
author: windows-driver-content
description: The WdfPdoInitAddDeviceText method adds a device description and device location to a device, for a specified locale.
old-location: wdf\wdfpdoinitadddevicetext.htm
old-project: wdf
ms.assetid: e46a9aee-8d96-41f5-b0f9-01846fefe4cb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfPdoInitAddDeviceText
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfPdoInitAddDeviceText
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoInitAddDeviceText function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAddDeviceText</b> method adds a device description and device location to a device, for a specified locale.



## -syntax

````
NTSTATUS WdfPdoInitAddDeviceText(
  _In_ PWDFDEVICE_INIT  DeviceInit,
  _In_ PCUNICODE_STRING DeviceDescription,
  _In_ PCUNICODE_STRING DeviceLocation,
  _In_ LCID             LocaleId
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceDescription [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a device description, formatted for the given locale. The driver can allocate the string's buffer from paged pool.


### -param DeviceLocation [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a description of the location on the bus where the parent device found the child. The driver can allocate the string's buffer from paged pool.


### -param LocaleId [in]

A locale identifier (LCID) that represents the locale of the Unicode strings. For more information, see <a href="https://msdn.microsoft.com/ea45b0e5-7df7-47fb-8dad-fccfbe53fec0">Locale Identifiers</a>.


## -returns
If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The driver is initializing an FDO instead of a PDO.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The driver could not allocate space to store the strings.

 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The framework stores the specified device text and passes it to the PnP manager in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551674">IRP_MN_QUERY_DEVICE_TEXT</a> request. The text that you supply should help the user to identify the device. The PnP manager sometimes displays the text while attempting to install additional drivers for the device.

You can call <b>WdfPdoInitAddDeviceText</b> multiple times, adding device text for multiple locales. When the system displays the text, it chooses the text that matches the current locale, if available. Otherwise, it will use the string for the default locale. The driver can specify the driver's default locale by calling <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitsetdefaultlocale.md">WdfPdoInitSetDefaultLocale</a>.

The driver must call <b>WdfPdoInitAddDeviceText</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The following code example provides Unicode strings for a device's location and description. The description includes an instance number. For a complete example that uses <b>WdfPdoInitAddDeviceText</b>, see the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver.


## -see-also
<dl>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitsetdefaultlocale.md">WdfPdoInitSetDefaultLocale</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoInitAddDeviceText method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

