---
UID: NC:wdfdevice.EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX
title: EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX
author: windows-driver-content
description: A driver's EvtDeviceUsageNotificationEx event callback function determines whether a device can support a special file type.
old-location: wdf\evtdeviceusagenotificationex.htm
tech.root: wdf
ms.assetid: A5C3E247-4883-4BFE-B36A-45AA989F36C9
ms.date: 02/26/2018
ms.keywords: EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX, EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback, EvtDeviceUsageNotificationEx, EvtDeviceUsageNotificationEx callback function, kmdf.evtdeviceusagenotificationex, wdf.evtdeviceusagenotificationex, wdfdevice/EvtDeviceUsageNotificationEx
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceUsageNotificationEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceUsageNotificationEx</i> event callback function determines whether a device can support a special file type.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552509">WDF_SPECIAL_FILE_TYPE</a>-typed value that identifies the type of special file that the system is storing on the specified device.


### -param IsInNotificationPath [in]

A Boolean value which, if <b>TRUE</b>, indicates that the system has starting using the special file and, if <b>FALSE</b>, indicates that the system has finished using the special file.


## -returns



If the driver determines that the device can support the special file, the <i>EvtDeviceUsageNotificationEx</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.




## -remarks



If your driver must provide driver-specific handling of special files, you must provide either an <i>EvtDeviceUsageNotificationEx</i> or an <a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a> event callback function. Do not provide both callback functions.

To register an <i>EvtDeviceUsageNotificationEx</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver's <i>EvtDeviceUsageNotificationEx</i> callback function returns a failure status, the framework propagates failure to other stacks that it may have notified earlier.

For more information about special files, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.


#### Examples

To define an <i>EvtDeviceUsageNotificationEx</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceUsageNotificationEx</i> callback function that is named <i>MyDeviceUsageNotificationEx</i>, use the <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX  MyDeviceUsageNotificationEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceUsageNotificationEx (
    WDFDEVICE  Device,
    WDF_SPECIAL_FILE_TYPE NotificationType,
    BOOLEAN  IsInNotificationPath
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.



