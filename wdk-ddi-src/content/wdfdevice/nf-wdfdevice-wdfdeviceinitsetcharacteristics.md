---
UID: NF:wdfdevice.WdfDeviceInitSetCharacteristics
title: WdfDeviceInitSetCharacteristics function
author: windows-driver-content
description: The WdfDeviceInitSetCharacteristics method sets device characteristics for a specified device.
old-location: wdf\wdfdeviceinitsetcharacteristics.htm
old-project: wdf
ms.assetid: 2937d9f1-f838-4ec4-972d-21ff43097590
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.wdfdeviceinitsetcharacteristics, kmdf.wdfdeviceinitsetcharacteristics, WdfDeviceInitSetCharacteristics, wdfdevice/WdfDeviceInitSetCharacteristics, WdfDeviceInitSetCharacteristics method, DFDeviceObjectGeneralRef_7dd76de2-8621-45ed-a309-c958ac1c365d.xml
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
-	WdfDeviceInitSetCharacteristics
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetCharacteristics function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetCharacteristics</b> method sets device characteristics for a specified device.


## -syntax


````
VOID WdfDeviceInitSetCharacteristics(
  _In_ PWDFDEVICE_INIT DeviceInit,
  _In_ ULONG           DeviceCharacteristics,
  _In_ BOOLEAN         OrInValues
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceCharacteristics [in]

A value that consists of ORed system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


### -param OrInValues [in]

A Boolean value. If this value is <b>TRUE</b>, the <i>DeviceCharacteristics</i> value is ORed with existing device characteristics. If the value is <b>FALSE</b>, the <i>DeviceCharacteristics</i> value replaces existing device characteristics.


## -returns



None




## -remarks



To set device characteristics, call the <b>WdfDeviceInitSetCharacteristics</b> method in your <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. If your driver cannot determine a device's characteristics until after the <i>EvtDriverDeviceAdd</i> callback function returns, call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetcharacteristics.md">WdfDeviceSetCharacteristics</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The framework always sets the FILE_DEVICE_SECURE_OPEN characteristic, so your driver does not have to set this characteristic.

Each call to <b>WdfDeviceInitSetCharacteristics</b> overwrites the settings of any previous call.


#### Examples

The following code example indicates that a device is a floppy disk.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetCharacteristics(
                                DeviceInit,
                                FILE_FLOPPY_DISKETTE,
                                FALSE
                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetcharacteristics.md">WdfDeviceSetCharacteristics</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetCharacteristics method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

