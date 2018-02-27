---
UID: NF:storport.StorPortLogTelemetry
title: StorPortLogTelemetry function
author: windows-driver-content
description: The StorPortLogTelemetry routine logs a miniport telemetry event to help diagnose or collect any useful information.
old-location: storage\storportlogtelemetry.htm
old-project: storage
ms.assetid: 3B32F31C-3850-43D4-9C6E-40D35B8AF4D4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortLogTelemetry, StorPortLogTelemetry routine [Storage Devices], storage.storportlogtelemetry, storport/StorPortLogTelemetry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortLogTelemetry
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortLogTelemetry function


## -description


The <b>StorPortLogTelemetry</b> routine logs a miniport telemetry event to help diagnose or collect any useful information. The miniport can log eight general purpose name-value pairs and a buffer that has maximum length of 4KB, as well as several event related fields that are defined in structure <a href="..\storport\ns-storport-_storport_telemetry_event.md">STORPORT_TELEMETRY_EVENT</a>.


## -syntax


````
ULONG StorPortLogTelemetry(
  _In_     PVOID                     HwDeviceExtension ,
  _In_opt_ PSTOR_ADDRESS             StorAddress,
  _In_     PSTORPORT_TELEMETRY_EVENT Event
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param StorAddress [in, optional]

The storage unit device address. This parameter is NULL for adapter devices.


### -param Event [in]

Pointer to the <a href="..\storport\ns-storport-_storport_telemetry_event.md">STORPORT_TELEMETRY_EVENT</a> structure that contains the telemetry data payload.


## -returns



<b>StorPortLogTelemetry </b>returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
<b>	EventBufferLength</b> is larger than <b>EVENT_BUFFER_MAX_LENGTH</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer to one of the parameters is NULL or the EventBufferLength/EventBuffer in Event structure not matching.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The telemetry event data have been successfully logged.

</td>
</tr>
</table>
 




## -remarks



If any parameter in Event structure is not named, Event-&gt;ParameterNameX == NULL, the routine will set the corresponding parameter value to 0.

If miniport has no payload to fill in Event-&gt;EventBuffer, it should set Event-&gt;EventBufferLength = 0, as well as Event-&gt;EventBuffer = NULL.





## -see-also

<a href="..\storport\ns-storport-_storport_telemetry_event.md">STORPORT_TELEMETRY_EVENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortLogTelemetry routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

