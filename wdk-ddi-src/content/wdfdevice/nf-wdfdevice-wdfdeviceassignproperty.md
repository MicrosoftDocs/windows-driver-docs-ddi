---
UID: NF:wdfdevice.WdfDeviceAssignProperty
title: WdfDeviceAssignProperty function
author: windows-driver-content
description: The WdfDeviceAssignProperty method modifies the current setting of a device property.
old-location: wdf\wdfdeviceassignproperty.htm
old-project: wdf
ms.assetid: 5110C452-53E6-401A-9D14-EBD95D3F8BE2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceAssignProperty method, WdfDeviceAssignProperty, wdfdevice/WdfDeviceAssignProperty, PFN_WDFDEVICEASSIGNPROPERTY, wdf.wdfdeviceassignproperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: APC_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceAssignProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignProperty function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAssignProperty</b> method modifies the current setting of a device property.


## -syntax


````
NTSTATUS WdfDeviceAssignProperty(
  _In_     WDFDEVICE                 Device,
  _In_     PWDF_DEVICE_PROPERTY_DATA DeviceProperty,
  _In_     DEVPROPTYPE               Type,
  _In_     ULONG                     Size,
  _In_opt_ PVOID                     Data
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceProperty [in]

A pointer to a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to modify.


### -param Type [in]

A <b>DEVPROPTYPE</b>-typed variable that specifies the type of the data stored in <i>Data</i>.


### -param Size [in]

The size, in bytes, of the buffer that is pointed to by <i>Data</i>.


### -param Data [in, optional]

A pointer to a caller-allocated buffer that contains the device property data. Set this parameter to <b>NULL</b> to delete the specified property.


## -returns


If the operation succeeds, <b>WdfDeviceAssignProperty</b> returns STATUS_SUCCESS. Additional return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is incorrect.

</td>
</tr>
</table> 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


You can use <b>WdfDeviceAssignProperty</b> to modify the setting of any property that is exposed through the unified property model.

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAssignProperty method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

