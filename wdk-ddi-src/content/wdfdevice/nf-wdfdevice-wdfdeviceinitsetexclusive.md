---
UID: NF:wdfdevice.WdfDeviceInitSetExclusive
title: WdfDeviceInitSetExclusive function
author: windows-driver-content
description: The WdfDeviceInitSetExclusive method indicates whether a specified device is an exclusive device.
old-location: wdf\wdfdeviceinitsetexclusive.htm
old-project: wdf
ms.assetid: 4bbcf4d3-e1f9-4e13-ac56-92ffddea1f67
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, DFDeviceObjectGeneralRef_fb2fbd3a-e78a-4632-b84f-b3e62a6efc94.xml, E, I, S, W, WdfDeviceInitSetExclusive, WdfDeviceInitSetExclusive method, c, d, e, f, i, kmdf.wdfdeviceinitsetexclusive, l, n, s, t, u, v, wdf.wdfdeviceinitsetexclusive, wdfdevice/WdfDeviceInitSetExclusive, x"
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
-	WdfDeviceInitSetExclusive
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetExclusive function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetExclusive</b> method indicates whether a specified device is an exclusive device.


## -syntax


````
VOID WdfDeviceInitSetExclusive(
  _In_ PWDFDEVICE_INIT DeviceInit,
  _In_ BOOLEAN         IsExclusive
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param IsExclusive [in]

A Boolean value which, if <b>TRUE</b>, indicates that the device is an exclusive device. If <b>FALSE</b>, the device is not an exclusive device.


## -returns



None




## -remarks



If a driver calls <b>WdfDeviceInitSetExclusive</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

If a driver calls <b>WdfDeviceInitSetExclusive</b>, only that driver's device object is exclusive. To make a device's entire device stack exclusive, the device's INF file should include an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/inf-addreg-directive">INF AddReg directive</a> that sets an <b>Exclusive</b> entry to <b>TRUE</b> in the registry.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


      If you are writing a UMDF driver, you  must modify your driver's INF file or make registry changes to indicate whether the device is exclusive. For more information about using the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563759">Setting Device Object Registry Properties During Installation</a>.


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

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetExclusive method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

