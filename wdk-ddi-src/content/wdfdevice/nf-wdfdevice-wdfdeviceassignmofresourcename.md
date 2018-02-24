---
UID: NF:wdfdevice.WdfDeviceAssignMofResourceName
title: WdfDeviceAssignMofResourceName function
author: windows-driver-content
description: The WdfDeviceAssignMofResourceName method registers a MOF resource name for a specified device.
old-location: wdf\wdfdeviceassignmofresourcename.htm
old-project: wdf
ms.assetid: b4ab0a7b-9c5a-4295-94fc-35310ca8e05b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_8cdcec0f-02df-4e8d-83e2-ae1fdc11343d.xml, kmdf.wdfdeviceassignmofresourcename, WdfDeviceAssignMofResourceName method, wdf.wdfdeviceassignmofresourcename, wdfdevice/WdfDeviceAssignMofResourceName, WdfDeviceAssignMofResourceName
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceAssignMofResourceName
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignMofResourceName function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceAssignMofResourceName</b> method registers a MOF resource name for a specified device.


## -syntax


````
NTSTATUS WdfDeviceAssignMofResourceName(
  _In_ WDFDEVICE        Device,
  _In_ PCUNICODE_STRING MofResourceName
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param MofResourceName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the name of a MOF resource. 


## -returns



If the operation succeeds, <b>WdfDeviceAssignMofResourceName</b> returns STATUS_SUCCESS. Additional return values include:

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
The driver has already called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignmofresourcename.md">WdfDeviceAssignMofResourceName</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 Insufficient memory is available.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver that provides a MOF file to support WMI must call <b>WdfDeviceAssignMofResourceName</b>, typically from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. The MOF resource name is the file name that the driver specifies in a <b>MofResource</b> statement in its resource script (RC) file. For more information about specifying a MOF resource name, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542012">Compiling a Driver's MOF File</a>.

A driver that <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">enumerates the devices on a bus</a> can call <b>WdfDeviceAssignMofResourceName</b> for the parent device, and the framework will use the parent's MOF resource name for child devices.

For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example declares a Unicode string that represents a MOF resource name and then registers the name.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
DECLARE_CONST_UNICODE_STRING(mofRsrcName, MOFRESOURCENAME);

status = WdfDeviceAssignMofResourceName(
                                        Device,
                                        &amp;mofRsrcName
                                        );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>


