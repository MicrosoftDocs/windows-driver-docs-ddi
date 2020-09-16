---
UID: NF:wdfpdo.WdfPdoInitAssignRawDevice
title: WdfPdoInitAssignRawDevice function (wdfpdo.h)
description: The WdfPdoInitAssignRawDevice method indicates that the calling driver can support a specified device in raw mode.
old-location: wdf\wdfpdoinitassignrawdevice.htm
tech.root: wdf
ms.assetid: 419912d0-40d0-4fa9-be3b-770875271640
ms.date: 02/26/2018
keywords: ["WdfPdoInitAssignRawDevice function"]
ms.keywords: DFDeviceObjectFdoPdoRef_afe4967c-d7ea-4c78-98ff-9bcfb98f6b80.xml, WdfPdoInitAssignRawDevice, WdfPdoInitAssignRawDevice method, kmdf.wdfpdoinitassignrawdevice, wdf.wdfpdoinitassignrawdevice, wdfpdo/WdfPdoInitAssignRawDevice
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2,  PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfPdoInitAssignRawDevice
 - wdfpdo/WdfPdoInitAssignRawDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfPdoInitAssignRawDevice
---

# WdfPdoInitAssignRawDevice function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitAssignRawDevice</b> method indicates that the calling driver can support a specified device in raw mode.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param DeviceClassGuid 

[in]
A pointer to a GUID that identifies a <a href="https://docs.microsoft.com/windows/win32/api/setupapi/ns-setupapi-sp_devinfo_data">device setup class</a>.

**Note**    You should always specify a custom class GUID. You should not specify an existing class GUID. If you specify an existing class GUID, other drivers that attempt to specify that existing class GUID might fail to install or might install with incorrect security settings.

For more information, see the following Remarks section.

## -returns

If the operation succeeds, the method returns STATUS_SUCCESS. Otherwise it returns STATUS_INVALID_PARAMETER.

## -remarks

The driver must call <b>WdfPdoInitAssignRawDevice</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The registry can contain values that override the values that a driver specifies when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetdevicetype">WdfDeviceInitSetDeviceType</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics">WdfDeviceInitSetCharacteristics</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetexclusive">WdfDeviceInitSetExclusive</a>. The <b>WdfPdoInitAssignRawDevice</b> method's <i>DeviceClassGuid</i> parameter specifies a GUID that identifies the section of the registry that contains the override values. The <i>DeviceClassGuid</i> parameter only identifies a section of the registry and does not actually set the <a href="https://docs.microsoft.com/windows/win32/api/setupapi/ns-setupapi-sp_devinfo_data">device setup class</a> for the device. The <a href="https://docs.microsoft.com/windows-hardware/drivers/install/inf-version-section">INF Version section</a> in your device and driver's INF file sets the device setup class. Typically, the <i>DeviceClassGuid</i> parameter's GUID should match the GUID that the <b>INF Version section</b> specifies. 

For more information about using the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/setting-device-object-registry-properties-after-installation">Setting Device Object Registry Properties After Installation</a>.


#### Examples

The following snippet from the kmdf_enumswitches driver sample indicates that a driver can support the specified device in raw mode.

```cpp
NTSTATUS  status;
DEFINE_GUID(GUID_DEVCLASS_MYUNIQUEID,
0xf149fe88, 0x f6cc, 0x47e3, 0x85, 0x94, 0xe2, 0xaa, 0xb6, 0xe0, 0x3b, 0xdf);

status = WdfPdoInitAssignRawDevice(
                                   pDeviceInit,
                                   &GUID_DEVCLASS_MYUNIQUEID
                                   );

```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics">WdfDeviceInitSetCharacteristics</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetdevicetype">WdfDeviceInitSetDeviceType</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetexclusive">WdfDeviceInitSetExclusive</a>

