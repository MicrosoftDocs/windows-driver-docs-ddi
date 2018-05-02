---
UID: NF:wudfddi.IWDFDevice.PostEvent
title: IWDFDevice::PostEvent
author: windows-driver-content
description: The PostEvent method asynchronously notifies applications that are waiting for the specified event from a driver.
old-location: wdf\iwdfdevice_postevent.htm
old-project: wdf
ms.assetid: 3df25c91-d421-48fe-958c-48bce3bc78b8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDevice interface,PostEvent method, IWDFDevice.PostEvent, IWDFDevice::PostEvent, PostEvent, PostEvent method, PostEvent method,IWDFDevice interface, UMDFDeviceObjectRef_7ba57249-59f4-4782-8846-717edf86dde1.xml, umdf.iwdfdevice_postevent, wdf.iwdfdevice_postevent, wudfddi/IWDFDevice::PostEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.PostEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::PostEvent


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>PostEvent</b> method asynchronously notifies applications that are waiting for the specified event from a driver.


## -parameters




### -param EventGuid [in]

The GUID for the event. The GUID is determined by the application and the driver and is opaque to the framework.


### -param EventType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265637">WDF_EVENT_TYPE</a>-typed value that identifies the type of event. In the current version of UMDF, the driver must set <i>EventType</i> to <b>WdfEventBroadcast</b> (1). <b>WdfEventBroadcast</b> indicates that the event is broadcast. Applications can subscribe to <b>WdfEventBroadcast</b>-type events. To receive broadcast events, the application must register for notification through the Microsoft Win32 <b>RegisterDeviceNotification</b> function. <b>WdfEventBroadcast</b>-type events are exposed as DBT_CUSTOMEVENT-type events to applications.


### -param pbData [in]

A pointer to a buffer that contains data that is associated with the event. <b>NULL</b> is a valid value. 


### -param cbDataSize [in]

The size, in bytes, of data that <i>pbData</i> points to. Zero is a valid size value if <i>pbData</i> is set to <b>NULL</b>. 

The maximum size of the event data is slightly less than MAXUSHORT (64 KB). The precise upper limit is (0xFFFF - <a href="https://msdn.microsoft.com/library/windows/hardware/ff545727">FIELD_OFFSET</a>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>, CustomDataBuffer)). 


## -returns



<b>PostEvent</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The event data was successfully sent to the operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_ENOUGH_MEMORY)</b></dt>
</dl>
</td>
<td width="60%">
The data size that the <i>cbDataSize</i> parameter specifies is larger than the maximum allowable size. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The <i>EventType</i> parameter is not set to <b>WdfEventBroadcast</b> (1). 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/3df25c91-d421-48fe-958c-48bce3bc78b8">PostEvent</a> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 

<b>PostEvent</b> might also return other HRESULT values.




## -remarks



When the driver calls <b>IWDFDevice::PostEvent</b> to notify the requesting application about an event, UMDF sends the event to the operating system. The operating system sends the event on to the requesting application in an asynchronous operation. If the operating system initially returns no error, the driver receives no error (S_OK). However, later, if the operating system receives an error while it attempts to deliver the event (possibly because of a low memory condition), the operating system is unable to inform the driver about the error. Because of the asynchronous nature of this event notification, delivery of the event to the requesting application is not guaranteed. If event information is lost on its way up to the requesting application, the application should be able to recover from the lost event. 

For information about creating device events, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545727">FIELD_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265606">WdfDevicePostEvent</a>
 

 

