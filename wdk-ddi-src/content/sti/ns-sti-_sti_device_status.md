---
UID: NS:sti._STI_DEVICE_STATUS
title: "_STI_DEVICE_STATUS"
author: windows-driver-content
description: The STI_DEVICE_STATUS structure is used as a parameter to the IStiDevice::GetStatus and IStiUSD::GetStatus methods.
old-location: image\sti_device_status.htm
old-project: Image
ms.assetid: 40104e1f-b936-430b-9e8c-28738579f4c7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sti/STI_DEVICE_STATUS, *PSTI_DEVICE_STATUS, STI_DEVICE_STATUS structure [Imaging Devices], _STI_DEVICE_STATUS, PSTI_DEVICE_STATUS structure pointer [Imaging Devices], PSTI_DEVICE_STATUS, image.sti_device_status, sti/PSTI_DEVICE_STATUS, stifnc_9581d5c4-a5c5-4115-8e9e-33f3da4806c6.xml, STI_DEVICE_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sti.h
apiname:
-	STI_DEVICE_STATUS
product: Windows
targetos: Windows
req.typenames: "*PSTI_DEVICE_STATUS, STI_DEVICE_STATUS"
req.product: Windows 10 or later.
---

# _STI_DEVICE_STATUS structure


## -description


The STI_DEVICE_STATUS structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543823">IStiUSD::GetStatus</a> methods.


## -syntax


````
typedef struct _STI_DEVICE_STATUS {
  DWORD dwSize;
  DWORD StatusMask;
  DWORD dwOnlineState;
  DWORD dwHardwareStatusCode;
  DWORD dwEventHandlingState;
  DWORD dwPollingInterval;
} STI_DEVICE_STATUS, *PSTI_DEVICE_STATUS;
````


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STI_DEVICE_STATUS structure.


### -field StatusMask

One or more caller-supplied bit flags, indicating the type of status information being requested. The following flags are defined:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
STI_DEVSTATUS_EVENTS_STATE

</td>
<td>
The driver should fill in the <b>dwEventHandlingState</b> member.

</td>
</tr>
<tr>
<td>
STI_DEVSTATUS_ONLINE_STATE 

</td>
<td>
The driver should fill in the <b>dwOnlineState</b> member.

</td>
</tr>
</table>
 


### -field dwOnlineState

Bit flags indicating the device's current status. The following flags are defined in <i>Sti.h</i>.

Currently use of STI_ONLINESTATE_OPERATIONAL is required, while use of all other flags is optional. (Currently, STI_ONLINESTATE_OPERATIONAL is the only flag that the still image server checks.)





#### STI_ONLINESTATE_BUSY

The device is busy.





#### STI_ONLINESTATE_ERROR

The device has reported an error.





#### STI_ONLINESTATE_INITIALIZING

The device is being initialized.





#### STI_ONLINESTATE_IO_ACTIVE

The device is active but not accepting commands.





#### STI_ONLINESTATE_OFFLINE

The device is off-line.





#### STI_ONLINESTATE_OPERATIONAL

The device is online and ready. If set, Control Panel indicates the device is ready. Otherwise, it indicates the device is off-line.





#### STI_ONLINESTATE_PAPER_JAM

The device has reported a paper jam.





#### STI_ONLINESTATE_PAPER_PROBLEM

The device has reported an unspecified paper problem.





#### STI_ONLINESTATE_PAUSED

The device is paused.





#### STI_ONLINESTATE_PENDING

I/O operations are pending.





#### STI_ONLINESTATE_POWER_SAVE

The device is in power save mode.





#### STI_ONLINESTATE_TRANSFERRING

The device is transferring data.





#### STI_ONLINESTATE_USER_INTERVENTION

The device requires user intervention.





#### STI_ONLINESTATE_WARMING_UP

The device is warming up.


### -field dwHardwareStatusCode

Optional device-specific, vendor-defined value.


### -field dwEventHandlingState

Contains bit flags indicating event status. The following flags are defined in <i>Sti.h</i>.





#### STI_EVENTHANDLING_ENABLED

<i>Not used</i>.





#### STI_EVENTHANDLING_PENDING

A device event has occurred.





#### STI_EVENTHANDLING_POLLING

<i>Not used</i>.


### -field dwPollingInterval

Time value, in milliseconds, indicating how often the device should be polled, if polling is required.

