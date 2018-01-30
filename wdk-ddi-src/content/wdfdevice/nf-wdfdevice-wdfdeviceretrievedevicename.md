---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceName
title: WdfDeviceRetrieveDeviceName function
author: windows-driver-content
description: The WdfDeviceRetrieveDeviceName method returns the device name for a specified device.
old-location: wdf\wdfdeviceretrievedevicename.htm
old-project: wdf
ms.assetid: 26fdc802-e28b-47a0-b248-5403d024fea3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WdfDeviceRetrieveDeviceName, WdfDeviceRetrieveDeviceName method, wdf.wdfdeviceretrievedevicename, WdfDeviceRetrieveDeviceName, PFN_WDFDEVICERETRIEVEDEVICENAME, DFDeviceObjectGeneralRef_8c3bab28-12f1-456b-a972-37444e81c847.xml, kmdf.wdfdeviceretrievedevicename
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
-	WdfDeviceRetrieveDeviceName
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceRetrieveDeviceName function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceRetrieveDeviceName</b> method returns the device name for a specified device.


## -syntax


````
NTSTATUS WdfDeviceRetrieveDeviceName(
  _In_ WDFDEVICE Device,
  _In_ WDFSTRING String
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param String [in]

A handle to a framework string object that receives the device name.


## -returns


If the operation succeeds, <b>WdfDeviceRetrieveDeviceName</b> returns STATUS_SUCCESS. Additional return values include:
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
An invalid parameter was detected.

</td>
</tr>
</table> 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


The <b>WdfDeviceRetrieveDeviceName</b> method returns the device name that the driver specified in a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignname.md">WdfDeviceInitAssignName</a>.

To obtain the device name string from the string object, the driver can call <a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>

<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignname.md">WdfDeviceInitAssignName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceRetrieveDeviceName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

