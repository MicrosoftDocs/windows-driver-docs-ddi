---
UID: NF:strmini.StreamClassDeviceNotification
title: StreamClassDeviceNotification function
author: windows-driver-content
description: Minidrivers use the StreamClassDeviceNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
old-location: stream\streamclassdevicenotification.htm
old-project: stream
ms.assetid: 80383159-c2c3-4d05-92e8-9245408e5243
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , C, D, N, S, StreamClassDeviceNotification, StreamClassDeviceNotification routine [Streaming Media Devices], a, c, e, f, i, l, m, n, o, r, s, strclass-routines_bddec484-f87c-4ebc-b8e1-ea52d265cbc4.xml, stream.streamclassdevicenotification, strmini/StreamClassDeviceNotification, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Stream.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Stream.lib
-	Stream.dll
apiname:
-	StreamClassDeviceNotification
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassDeviceNotification function


## -description


Minidrivers use the <b>StreamClassDeviceNotification</b> routine to notify the class driver that it has completed a stream request, or that an event has occurred.


## -syntax


````
VOID  StreamClassDeviceNotification(
  _In_ STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE NotificationType,
  _In_ PVOID                                      HwDeviceExtension,
       PHW_STREAM_REQUEST_BLOCK                   pSrb,
       PKSEVENT_ENTRY                             EventEntry,
       GUID                                       *EventSet,
       ULONG                                      EventId
);
````


## -parameters




### -param NotificationType [in]

This is an enumeration value that contains the type of notification that the minidriver is sending.





#### DeviceRequestComplete

Indicates that the minidriver has completed its handling of the device stream request block pointed to by the optional third argument of this routine, <i>pSrb</i>. Once the minidriver calls <b>StreamClassDeviceNotification</b> with this value, the relevant SRB is owned by the class driver, which is free to deallocate it.



#### ReadyForNextDeviceRequest

Indicates that the minidriver is ready to receive another device request. 



#### SignalDeviceEvent

Signals that the event specified by the <i>EventEntry</i> parameter has occurred.



#### SignalMultipleDeviceEvents

Signals all events that match the criteria specified in the <i>EventSet</i> and <i>EventId</i> parameters.



#### DeleteDeviceEvent

Deletes the event specified by the <i>EventEntry</i> parameter. 


### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\storport\ns-storport-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param param

TBD




#### - pSrb

Pointer to an <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a> structure. If <i>NotificationType</i> equals <b>DeviceRequestComplete</b>, this parameter points to the stream request block that the minidriver has completed processing. After <b>StreamClassDeviceNotification</b> completes, this address is no longer valid.


#### - EventEntry

If <i>NotificationType</i> equals either SignalDeviceEvent or DeleteDeviceEvent, points to a structure of type <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> that specifies the event to be signaled or deleted. 


#### - EventSet

Specifies the event set to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>. 


#### - EventId

Specifies the event ID to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>.


## -returns



None




## -remarks



The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a>.




## -see-also

<a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassDeviceNotification routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

