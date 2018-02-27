---
UID: NF:wdfdevice.WdfDevicePostEvent
title: WdfDevicePostEvent function
author: windows-driver-content
description: The WdfDevicePostEvent method asynchronously notifies applications that are waiting for the specified event from a driver.
old-location: wdf\wdfdevicepostevent.htm
old-project: wdf
ms.assetid: A482CCB8-D7C6-48B6-900D-73CD0EF3B296
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDevicePostEvent, WdfDevicePostEvent function, wdf.wdfdevicepostevent, wdfdevice/WdfDevicePostEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDevicePostEvent
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDevicePostEvent function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDevicePostEvent</b> method asynchronously notifies applications that are waiting for the       specified event from a driver.


## -syntax


````
NTSTATUS WdfDevicePostEvent(
  _In_ WDFDEVICE      Device,
  _In_ REFGUID        EventGuid,
  _In_ WDF_EVENT_TYPE WdfEventType,
  _In_ BYTE           *Data,
  _In_ ULONG          DataSizeCb
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param EventGuid [in]

The GUID for the event. The GUID is determined by the application and the driver and is opaque to the framework.


### -param WdfEventType [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_event_type.md">WDF_EVENT_TYPE</a>-typed value that identifies the type of event. In the current version of UMDF, the driver must set <i>EventType</i> to <b>WdfEventBroadcast</b> (1). <b>WdfEventBroadcast</b> indicates that the event is broadcast. Applications can subscribe to <b>WdfEventBroadcast</b>-type events. To receive broadcast events, the application must register for notification through the Microsoft Win32 <b>RegisterDeviceNotification</b> function. <b>WdfEventBroadcast</b>-type events are exposed as DBT_CUSTOMEVENT-type events to applications.


### -param Data [in]

A pointer to a buffer that contains data that is associated with the event. <b>NULL</b> is a valid value. 


### -param DataSizeCb [in]

The size, in bytes, of data that <i>Data</i> points to. Zero is a valid size value if <i>Data</i> is set to <b>NULL</b>. 


## -returns



If the operation succeeds, <b>WdfDevicePostEvent</b> returns STATUS_SUCCESS. Additional return values include:

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
<i>WdfEventType</i> is not set to <b>WdfEventBroadcast</b>.


</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



When the driver calls <b>WdfDevicePostEvent</b> to notify the requesting application about an event, UMDF sends the event to the operating system. The operating system sends the event on to the requesting application in an asynchronous operation. If the operating system initially returns no error, <b>WdfDevicePostEvent</b> returns STATUS_SUCCESS.

 However, later, if the operating system receives an error while it attempts to deliver the event (possibly because of a low memory condition), the operating system is unable to inform the driver about the error. Because of the asynchronous nature of this event notification, delivery of the event to the requesting application is not guaranteed.

 If event information is lost on its way up to the requesting application, the application should be able to recover from the lost event. 




## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_event_type.md">WDF_EVENT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558835">IWDFDevice::PostEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDevicePostEvent function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

