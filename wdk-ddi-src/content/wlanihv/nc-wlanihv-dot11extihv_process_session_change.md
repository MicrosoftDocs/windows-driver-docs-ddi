---
UID: NC:wlanihv.DOT11EXTIHV_PROCESS_SESSION_CHANGE
title: DOT11EXTIHV_PROCESS_SESSION_CHANGE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvprocesssessionchange.htm
old-project: netvista
ms.assetid: 17d5ab30-141a-4b7b-93f1-113fb1a39ba6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvprocesssessionchange, Dot11ExtIhvProcessSessionChange callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvProcessSessionChange, DOT11EXTIHV_PROCESS_SESSION_CHANGE, DOT11EXTIHV_PROCESS_SESSION_CHANGE, wlanihv/Dot11ExtIhvProcessSessionChange, Native_802.11_IHV_Ext_158881c6-a8ae-4155-a2e6-549a47c3fce1.xml
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
-	UserDefined
apilocation: 
-	wlanihv.h
apiname: 
-	Dot11ExtIhvProcessSessionChange
product: Windows
targetos: Windows
req.typenames: *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PROCESS_SESSION_CHANGE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvProcessSessionChange</i> function to notify the IHV Extensions DLL of a session change
  event.


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
    requests.


