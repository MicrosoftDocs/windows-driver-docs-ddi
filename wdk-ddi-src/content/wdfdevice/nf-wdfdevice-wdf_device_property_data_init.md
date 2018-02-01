---
UID: NF:wdfdevice.WDF_DEVICE_PROPERTY_DATA_INIT
title: WDF_DEVICE_PROPERTY_DATA_INIT function
author: windows-driver-content
description: The WDF_DEVICE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_PROPERTY_DATA structure.
old-location: wdf\wdf_device_property_data_init.htm
old-project: wdf
ms.assetid: D3A7646A-49A8-499E-A63A-BCD222DF7804
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_DEVICE_PROPERTY_DATA_INIT, wdf.wdf_device_property_data_init, WDF_DEVICE_PROPERTY_DATA_INIT function, wdfdevice/WDF_DEVICE_PROPERTY_DATA_INIT
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_DEVICE_PROPERTY_DATA_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_DEVICE_PROPERTY_DATA_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure.


## -syntax


````
void WDF_DEVICE_PROPERTY_DATA_INIT(
  _In_       PWDF_DEVICE_INTERFACE_PROPERTY_DATA PropertyData,
  _In_ const DEVPROPKEY                          *PropertyKey
);
````


## -parameters




### -param PropertyData [in]

A pointer to <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure.


### -param PropertyKey [in]

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device property key.


## -returns


This function does not return a value.



## -remarks


Before calling the following methods, a driver must call <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> to initialize a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure.
<ul>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandquerypropertyex.md">WdfDeviceAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignproperty.md">WdfDeviceAssignProperty</a>
</li>
<li>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequerypropertyex.md">WdfDeviceQueryPropertyEx</a>
</li>
<li>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandquerypropertyex.md">WdfFdoInitAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitquerypropertyex.md">WdfFdoInitQueryPropertyEx</a>
</li>
</ul>The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>PropertyKey</b> member to the specified value.



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandquerypropertyex.md">WdfFdoInitAllocAndQueryPropertyEx</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitquerypropertyex.md">WdfFdoInitQueryPropertyEx</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignproperty.md">WdfDeviceAssignProperty</a>

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequerypropertyex.md">WdfDeviceQueryPropertyEx</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandquerypropertyex.md">WdfDeviceAllocAndQueryPropertyEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PROPERTY_DATA_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

