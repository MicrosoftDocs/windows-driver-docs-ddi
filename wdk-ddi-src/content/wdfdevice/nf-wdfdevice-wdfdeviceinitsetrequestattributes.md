---
UID: NF:wdfdevice.WdfDeviceInitSetRequestAttributes
title: WdfDeviceInitSetRequestAttributes function
author: windows-driver-content
description: The WdfDeviceInitSetRequestAttributes method sets object attributes that will be used for all of the framework request objects that the framework delivers to the driver from the device's I/O queues.
old-location: wdf\wdfdeviceinitsetrequestattributes.htm
old-project: wdf
ms.assetid: ac705ff9-8019-47f9-8842-05f9152af29c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_30c50afa-81a1-4f3c-a2b0-987920922a4f.xml, WdfDeviceInitSetRequestAttributes, WdfDeviceInitSetRequestAttributes method, kmdf.wdfdeviceinitsetrequestattributes, wdf.wdfdeviceinitsetrequestattributes, wdfdevice/WdfDeviceInitSetRequestAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceInitSetRequestAttributes
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetRequestAttributes function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceInitSetRequestAttributes</b> method sets object attributes that will be used for all of the framework request objects that the framework delivers to the driver from the device's I/O queues. 


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param RequestAttributes [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the device's request objects.


## -returns



None




## -remarks



Your driver can call <b>WdfDeviceInitSetRequestAttributes</b> to specify the object context space that the framework will assign to the request objects that it creates for your driver. For more information about this context space, see <a href="https://msdn.microsoft.com/befb4a22-0640-45e3-890e-6ff17969b017">Using Request Object Context</a>.

The framework does not use the specified object attributes for request objects that it creates when a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549953">WdfRequestCreateFromIrp</a>.

Your driver must call <b>WdfDeviceInitSetRequestAttributes</b> from within its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function, before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure and calls <b>WdfDeviceInitSetRequestAttributes</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _REQUEST_CONTEXT {
  ULONG_PTR  Information;
} REQUEST_CONTEXT, *PREQUEST_CONTEXT;
WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &amp;attributes,
                                        REQUEST_CONTEXT
                                        );
WdfDeviceInitSetRequestAttributes(
                                  DeviceInit,
                                  &amp;attributes
                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>
 

 

