---
UID: NF:wdfdevice.WdfDeviceInitSetDeviceType
title: WdfDeviceInitSetDeviceType function
author: windows-driver-content
description: The WdfDeviceInitSetDeviceType method sets the device type for a specified device.
old-location: wdf\wdfdeviceinitsetdevicetype.htm
tech.root: wdf
ms.assetid: 26c5c998-fb10-45c3-b28c-91a759fa941e
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_872eb4dd-0d40-46ed-a7ed-4eae8ec67240.xml, WdfDeviceInitSetDeviceType, WdfDeviceInitSetDeviceType method, kmdf.wdfdeviceinitsetdevicetype, wdf.wdfdeviceinitsetdevicetype, wdfdevice/WdfDeviceInitSetDeviceType
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitSetDeviceType
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetDeviceType function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetDeviceType</b> method sets the device type for a specified device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceType [in]

A FILE_DEVICE_XXXX value that identifies the device type. For more information about FILE_DEVICE_XXXX values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.


## -returns



None




## -remarks



If a driver calls <b>WdfDeviceInitSetDeviceType</b>, it must do so before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The device type that a driver specifies determines the default priority boost value that the framework uses when the driver completes an I/O request. For more information about priority boost values, see <a href="https://msdn.microsoft.com/9a501ca1-58c9-4458-b202-9581f8ce5e5f">Specifying Priority Boosts When Completing I/O Requests</a>.


      If you are writing a UMDF driver, you  must modify your driver's INF file or make registry changes to specify a device type. For more information about using the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563759">Setting Device Object Registry Properties During Installation</a>.


#### Examples

The following code example indicates that a device is a serial device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetDeviceType(
                           DeviceInit,
                           FILE_DEVICE_SERIAL_PORT
                           );</pre>
</td>
</tr>
</table></span></div>


