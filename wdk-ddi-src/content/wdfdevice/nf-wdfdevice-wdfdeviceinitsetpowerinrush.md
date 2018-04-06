---
UID: NF:wdfdevice.WdfDeviceInitSetPowerInrush
title: WdfDeviceInitSetPowerInrush function
author: windows-driver-content
description: The WdfDeviceInitSetPowerInrush method informs the power manager that the specified device requires an inrush of current when it starts.
old-location: wdf\wdfdeviceinitsetpowerinrush.htm
old-project: wdf
ms.assetid: 91b29a5b-8bc0-44c0-8c48-2d023da12dcb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_07e58947-78a3-4864-924c-8bd11dfd8af5.xml, WdfDeviceInitSetPowerInrush, WdfDeviceInitSetPowerInrush method, kmdf.wdfdeviceinitsetpowerinrush, wdf.wdfdeviceinitsetpowerinrush, wdfdevice/WdfDeviceInitSetPowerInrush
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
-	WdfDeviceInitSetPowerInrush
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPowerInrush function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetPowerInrush</b> method informs the power manager that the specified device requires an inrush of current when it starts.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



To avoid overloading the system's power supply, the system starts devices that require an inrush of current one at a time.

If your driver calls <b>WdfDeviceInitSetPowerInrush</b>, the framework makes it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">nonpageable</a> during power state transitions and the driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546766">WdfDeviceInitSetPowerPageable</a>. 

Your driver must call <b>WdfDeviceInitSetPowerInrush</b> before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

Calling <b>WdfDeviceInitSetPowerInrush</b> from a filter driver has no effect. For filter drivers, the framework uses the setting that the next-lower driver in the driver stack specifies.


#### Examples

The following code example informs the power manager that a device requires an inrush of current when it starts.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetPowerInrush(DeviceInit);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

