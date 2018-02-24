---
UID: NF:wdfdevice.WdfWdmDeviceGetWdfDeviceHandle
title: WdfWdmDeviceGetWdfDeviceHandle function
author: windows-driver-content
description: The WdfWdmDeviceGetWdfDeviceHandle method returns a handle to the framework device object that is associated with a specified WDM device object.
old-location: wdf\wdfwdmdevicegetwdfdevicehandle.htm
old-project: wdf
ms.assetid: 8083af10-1b35-4600-b409-e895d35f7ccc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfWdmDeviceGetWdfDeviceHandle method, DFDeviceObjectGeneralRef_0b05680a-5252-4932-802d-ee24a0092116.xml, wdf.wdfwdmdevicegetwdfdevicehandle, wdfdevice/WdfWdmDeviceGetWdfDeviceHandle, WdfWdmDeviceGetWdfDeviceHandle, kmdf.wdfwdmdevicegetwdfdevicehandle
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfWdmDeviceGetWdfDeviceHandle
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfWdmDeviceGetWdfDeviceHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWdmDeviceGetWdfDeviceHandle</b> method returns a handle to the framework device object that is associated with a specified WDM device object.


## -syntax


````
WDFDEVICE WdfWdmDeviceGetWdfDeviceHandle(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

A pointer to a WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that the calling driver created.


## -returns



If the specified WDM device object is valid, <b>WdfWdmDeviceGetWdfDeviceHandle</b> returns a handle to the associated framework device object. Otherwise, the method returns <b>NULL</b>.




## -remarks



The WDM DEVICE_OBJECT structure that the driver specifies for the <i>DeviceObject</i> parameter must represent a device object that the calling driver created. For example, the structure cannot represent any of the WDM device objects that the driver specified in a previous call to <a href="..\wdfminiport\nf-wdfminiport-wdfdeviceminiportcreate.md">WdfDeviceMiniportCreate</a>.


#### Examples

The following code example obtains a handle to the framework device object that is associated with a WDM device object that the calling driver created.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE  device;

device = WdfWdmDeviceGetWdfDeviceHandle(pWdmDeviceObject);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfminiport\nf-wdfminiport-wdfdeviceminiportcreate.md">WdfDeviceMiniportCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWdmDeviceGetWdfDeviceHandle method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

