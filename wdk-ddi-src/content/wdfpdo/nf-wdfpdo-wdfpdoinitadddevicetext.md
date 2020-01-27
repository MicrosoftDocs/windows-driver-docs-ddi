---
UID: NF:wdfpdo.WdfPdoInitAddDeviceText
title: WdfPdoInitAddDeviceText function (wdfpdo.h)
description: The WdfPdoInitAddDeviceText method adds a device description and device location to a device, for a specified locale.
old-location: wdf\wdfpdoinitadddevicetext.htm
tech.root: wdf
ms.assetid: e46a9aee-8d96-41f5-b0f9-01846fefe4cb
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_1167066a-5ec9-47b8-be03-32127121fa91.xml, WdfPdoInitAddDeviceText, WdfPdoInitAddDeviceText method, kmdf.wdfpdoinitadddevicetext, wdf.wdfpdoinitadddevicetext, wdfpdo/WdfPdoInitAddDeviceText
f1_keywords:
 - "wdfpdo/WdfPdoInitAddDeviceText"
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoInitAddDeviceText
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitAddDeviceText function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitAddDeviceText</b> method adds a device description and device location to a device, for a specified locale.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param DeviceDescription [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a device description, formatted for the given locale. The driver can allocate the string's buffer from paged pool.


### -param DeviceLocation [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a description of the location on the bus where the parent device found the child. The driver can allocate the string's buffer from paged pool.


### -param LocaleId [in]

A locale identifier (LCID) that represents the locale of the Unicode strings. For more information, see <a href="https://docs.microsoft.com/windows/desktop/Intl/locale-identifiers">Locale Identifiers</a>.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

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
The driver is initializing an FDO instead of a PDO.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The driver could not allocate space to store the strings.

</td>
</tr>
</table>
 

The method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The framework stores the specified device text and passes it to the PnP manager in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-text">IRP_MN_QUERY_DEVICE_TEXT</a> request. The text that you supply should help the user to identify the device. The PnP manager sometimes displays the text while attempting to install additional drivers for the device.

You can call <b>WdfPdoInitAddDeviceText</b> multiple times, adding device text for multiple locales. When the system displays the text, it chooses the text that matches the current locale, if available. Otherwise, it will use the string for the default locale. The driver can specify the driver's default locale by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitsetdefaultlocale">WdfPdoInitSetDefaultLocale</a>.

The driver must call <b>WdfPdoInitAddDeviceText</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example provides Unicode strings for a device's location and description. The description includes an instance number. For a complete example that uses <b>WdfPdoInitAddDeviceText</b>, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver.

```cpp
DECLARE_CONST_UNICODE_STRING(deviceLocation,L"Keyboard Filter\0" );
DECLARE_UNICODE_STRING_SIZE(buffer, MAX_ID_LEN);

status = RtlUnicodeStringPrintf(
                                &buffer,
                                L"Keyboard_Filter_%02d",
                                InstanceNo
                                );
if (!NT_SUCCESS(status)) {
    goto Cleanup;
}
status = WdfPdoInitAddDeviceText(
                                 pDeviceInit,
                                 &buffer,
                                 &deviceLocation,
                                 0x409
                                 );
if (!NT_SUCCESS(status)) {
    goto Cleanup;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitsetdefaultlocale">WdfPdoInitSetDefaultLocale</a>
 

 

