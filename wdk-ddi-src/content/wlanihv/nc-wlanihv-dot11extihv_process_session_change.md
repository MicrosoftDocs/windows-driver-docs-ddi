---
UID: NC:wlanihv.DOT11EXTIHV_PROCESS_SESSION_CHANGE
title: DOT11EXTIHV_PROCESS_SESSION_CHANGE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvprocesssessionchange.htm
old-project: netvista
ms.assetid: 17d5ab30-141a-4b7b-93f1-113fb1a39ba6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvProcessSessionChange
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PROCESS_SESSION_CHANGE callback



## -description

## -prototype

````
DOT11EXTIHV_PROCESS_SESSION_CHANGE Dot11ExtIhvProcessSessionChange;

DWORD APIENTRY Dot11ExtIhvProcessSessionChange(
  _In_ ULONG                    uEventType,
  _In_ PWTSSESSION_NOTIFICATION pSessionNotification
)
{ ... }
````


## -parameters

### -param uEventType [in]

The type of event. This parameter can have one of the following values.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WTS_CONSOLE_CONNECT

</td>
<td>
A session was connected to the console session.

</td>
</tr>
<tr>
<td>
WTS_CONSOLE_DISCONNECT

</td>
<td>
A session was disconnected from the console session.

</td>
</tr>
<tr>
<td>
WTS_REMOTE_CONNECT

</td>
<td>
A session was connected to the remote session.

</td>
</tr>
<tr>
<td>
WTS_REMOTE_DISCONNECT

</td>
<td>
A session was disconnected from the remote session.

</td>
</tr>
<tr>
<td>
WTS_SESSION_LOGON

</td>
<td>
A user has logged on to the session.

</td>
</tr>
<tr>
<td>
WTS_SESSION_LOGOFF

</td>
<td>
A user has logged off of the session.

</td>
</tr>
<tr>
<td>
WTS_SESSION_LOCK

</td>
<td>
A session has been locked.

</td>
</tr>
<tr>
<td>
WTS_SESSION_UNLOCK

</td>
<td>
A session has been unlocked.

</td>
</tr>
<tr>
<td>
WTS_SESSION_REMOTE_CONTROL

</td>
<td>
A session has changed its remote controlled status. To determine the status, call the 
        <b>GetSystemMetrics</b> function and check the SM_REMOTECONTROL metric. For more information about
        this function, refer to the Microsoft Windows SDK documentation.

</td>
</tr>
</table>
 


### -param pSessionNotification [in]

A pointer to a WTSSESSION_NOTIFICATION structure, which provides information about the session
     change notification. For more information about this structure, refer to the Windows SDK
     documentation.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
The operating system calls the function to notify the IHV Extensions DLL whenever a switch in a user
    session occurs.

If the 
    <i>uEventType</i> parameter is set to WTS_SESSION_LOGOFF, the IHV Extensions DLL must cancel all pending
    user interface requests internally and must release any allocated resources for the user interface
    requests.</p>