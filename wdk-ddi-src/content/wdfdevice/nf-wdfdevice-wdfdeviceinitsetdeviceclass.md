---
UID: NF:wdfdevice.WdfDeviceInitSetDeviceClass
title: WdfDeviceInitSetDeviceClass function
author: windows-driver-content
description: The WdfDeviceInitSetDeviceClass method specifies a GUID that identifies the device's device setup class.
old-location: wdf\wdfdeviceinitsetdeviceclass.htm
old-project: wdf
ms.assetid: c87a8368-3804-4a07-92c8-65a453d0808f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfdeviceinitsetdeviceclass, wdfdevice/WdfDeviceInitSetDeviceClass, DFDeviceObjectGeneralRef_9c2c2390-3dcc-40f4-ba43-16c8988dbfae.xml, WdfDeviceInitSetDeviceClass method, WdfDeviceInitSetDeviceClass, kmdf.wdfdeviceinitsetdeviceclass
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceInitSetDeviceClass
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetDeviceClass function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetDeviceClass</b> method specifies a GUID that identifies the device's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff552344">device setup class</a>. 


## -syntax


````
VOID WdfDeviceInitSetDeviceClass(
  _In_       PWDFDEVICE_INIT DeviceInit,
  _In_ const GUID            *DeviceClassGuid
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceClassGuid [in]

Pointer to a GUID that identifies a section of the registry containing possible overrides for the <i>DefaultSDDLString</i>, <i>DeviceType</i>, <i>DeviceCharacteristics</i>, and <i>Exclusive</i> parameters.
<div class="alert"><b>Note</b>    You should always specify a custom class GUID. You should not specify an existing class GUID. If you specify an existing class GUID, other drivers that attempt to specify that existing class GUID might fail to install or might install with incorrect security settings.</div><div> </div>

## -returns


None



## -remarks


The registry can contain values that override the values that a driver specifies when it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetdevicetype.md">WdfDeviceInitSetDeviceType</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetcharacteristics.md">WdfDeviceInitSetCharacteristics</a>, and <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetexclusive.md">WdfDeviceInitSetExclusive</a>. The driver can call <b>WdfDeviceInitSetDeviceClass</b> to specify a GUID that identifies the section of the registry that contains the override values.

Typically, a driver calls <b>WdfDeviceInitSetDeviceClass</b> only if it is creating a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">control device</a>. 

For more information about using the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563755">Setting Device Object Registry Properties After Installation</a>.

If a driver calls <b>WdfDeviceInitSetDeviceClass</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


