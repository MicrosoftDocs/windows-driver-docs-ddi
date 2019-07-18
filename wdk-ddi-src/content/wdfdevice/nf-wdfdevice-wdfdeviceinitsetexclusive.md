---
UID: NF:wdfdevice.WdfDeviceInitSetExclusive
title: WdfDeviceInitSetExclusive function (wdfdevice.h)
description: The WdfDeviceInitSetExclusive method indicates whether a specified device is an exclusive device.
old-location: wdf\wdfdeviceinitsetexclusive.htm
tech.root: wdf
ms.assetid: 4bbcf4d3-e1f9-4e13-ac56-92ffddea1f67
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_fb2fbd3a-e78a-4632-b84f-b3e62a6efc94.xml, WdfDeviceInitSetExclusive, WdfDeviceInitSetExclusive method, kmdf.wdfdeviceinitsetexclusive, wdf.wdfdeviceinitsetexclusive, wdfdevice/WdfDeviceInitSetExclusive
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceInitSetExclusive"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInitSetExclusive
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetExclusive function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetExclusive</b> method indicates whether a specified device is an exclusive device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param IsExclusive [in]

A Boolean value which, if <b>TRUE</b>, indicates that the device is an exclusive device. If <b>FALSE</b>, the device is not an exclusive device.


## -returns



None




## -remarks



If a driver calls <b>WdfDeviceInitSetExclusive</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

If a driver calls <b>WdfDeviceInitSetExclusive</b>, only that driver's device object is exclusive. To make a device's entire device stack exclusive, the device's INF file should include an <a href="https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive">INF AddReg directive</a> that sets an <b>Exclusive</b> entry to <b>TRUE</b> in the registry.

For more information about calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


      If you are writing a UMDF driver, you  must modify your driver's INF file or make registry changes to indicate whether the device is exclusive. For more information about using the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/setting-device-object-registry-properties-during-installation">Setting Device Object Registry Properties During Installation</a>.


#### Examples

The following code example indicates that a device is an exclusive device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetExclusive(
                          DeviceInit,
                          TRUE
                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
 

 

