---
UID: NF:wdfdevice.WdfDeviceInitSetDeviceClass
title: WdfDeviceInitSetDeviceClass function (wdfdevice.h)
description: The WdfDeviceInitSetDeviceClass method specifies a GUID that identifies the device's device setup class.
old-location: wdf\wdfdeviceinitsetdeviceclass.htm
tech.root: wdf
ms.assetid: c87a8368-3804-4a07-92c8-65a453d0808f
ms.date: 02/26/2018
keywords: ["WdfDeviceInitSetDeviceClass function"]
ms.keywords: DFDeviceObjectGeneralRef_9c2c2390-3dcc-40f4-ba43-16c8988dbfae.xml, WdfDeviceInitSetDeviceClass, WdfDeviceInitSetDeviceClass method, kmdf.wdfdeviceinitsetdeviceclass, wdf.wdfdeviceinitsetdeviceclass, wdfdevice/WdfDeviceInitSetDeviceClass
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitSetDeviceClass
 - wdfdevice/WdfDeviceInitSetDeviceClass
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceInitSetDeviceClass
---

# WdfDeviceInitSetDeviceClass function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetDeviceClass</b> method specifies a GUID that identifies the device's <a href="/windows/win32/api/setupapi/ns-setupapi-sp_devinfo_data">device setup class</a>.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param DeviceClassGuid 

[in]
Pointer to a GUID that identifies a section of the registry containing possible overrides for the <i>DefaultSDDLString</i>, <i>DeviceType</i>, <i>DeviceCharacteristics</i>, and <i>Exclusive</i> parameters.

<div class="alert"><b>Note</b>    You should always specify a custom class GUID. You should not specify an existing class GUID. If you specify an existing class GUID, other drivers that attempt to specify that existing class GUID might fail to install or might install with incorrect security settings.</div>
<div> </div>

## -remarks

The registry can contain values that override the values that a driver specifies when it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetdevicetype">WdfDeviceInitSetDeviceType</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics">WdfDeviceInitSetCharacteristics</a>, and <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetexclusive">WdfDeviceInitSetExclusive</a>. The driver can call <b>WdfDeviceInitSetDeviceClass</b> to specify a GUID that identifies the section of the registry that contains the override values.

Typically, a driver calls <b>WdfDeviceInitSetDeviceClass</b> only if it is creating a <a href="/windows-hardware/drivers/wdf/using-control-device-objects">control device</a>. 

For more information about using the registry, see <a href="/windows-hardware/drivers/kernel/setting-device-object-registry-properties-after-installation">Setting Device Object Registry Properties After Installation</a>.

If a driver calls <b>WdfDeviceInitSetDeviceClass</b>, it must do so before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example sets a device's setup class to the system device class.

```cpp
DEFINE_GUID(GUID_DEVCLASS_MYUNIQUEID,
0xf149fe88, 0x f6cc, 0x47e3, 0x85, 0x94, 0xe2, 0xaa, 0xb6, 0xe0, 0x3b, 0xdf);

WdfDeviceInitSetDeviceClass(
                            DeviceInit,
                            &GUID_DEVCLASS_MYUNIQUEID
                            );

```