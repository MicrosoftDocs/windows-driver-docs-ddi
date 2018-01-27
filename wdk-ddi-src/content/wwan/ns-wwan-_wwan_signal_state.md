---
UID: NS:wwan._WWAN_SIGNAL_STATE
title: _WWAN_SIGNAL_STATE
author: windows-driver-content
description: The WWAN_SIGNAL_STATE structure represents the signal state of the MB device.
old-location: netvista\wwan_signal_state.htm
old-project: netvista
ms.assetid: ba5632bb-c1d7-47b1-b6b4-88c67710149f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_SIGNAL_STATE structure [Network Drivers Starting with Windows Vista], *PWWAN_SIGNAL_STATE, _WWAN_SIGNAL_STATE, netvista.wwan_signal_state, PWWAN_SIGNAL_STATE, wwan/PWWAN_SIGNAL_STATE, WWAN_SIGNAL_STATE, WwanRef_6a92457b-8b82-4956-9dce-98e5aeec9091.xml, PWWAN_SIGNAL_STATE structure pointer [Network Drivers Starting with Windows Vista], wwan/WWAN_SIGNAL_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
apiname: 
-	WWAN_SIGNAL_STATE
product: Windows
targetos: Windows
req.typenames: *PWWAN_SIGNAL_STATE, WWAN_SIGNAL_STATE
req.product: Windows 10 or later.
---

# _WWAN_SIGNAL_STATE structure


## -description


The WWAN_SIGNAL_STATE structure represents the signal state of the MB device.


## -syntax


````
typedef struct _WWAN_SIGNAL_STATE {
  ULONG Rssi;
  ULONG ErrorRate;
  ULONG RssiInterval;
  ULONG RssiThreshold;
} WWAN_SIGNAL_STATE, *PWWAN_SIGNAL_STATE;
````


## -struct-fields




### -field Rssi

A value that represents the strength of the wireless signal. Miniport drivers that report their
     WWAN_CELLULAR_CLASS to be 
     <b>WwanCellularClassGSM</b> or 
     <b>WwanCellularClassCDMA</b> must report Rssi in decibels above the device's sensitivity noise floor.
     
<table>
<tr>
<th>Signal Strength (in dBm)</th>
<th>Coded Value (Minimum=0, Maximum=31)</th>
</tr>
<tr>
<td>
-113 or less

</td>
<td>
0

</td>
</tr>
<tr>
<td>
-111

</td>
<td>
1

</td>
</tr>
<tr>
<td>
-109

</td>
<td>
2

</td>
</tr>
<tr>
<td>
...

</td>
<td>
...

</td>
</tr>
<tr>
<td>
-51 or greater

</td>
<td>
31

</td>
</tr>
<tr>
<td>
Unknown or undetectable

</td>
<td>
WWAN_RSSI_UNKNOWN

</td>
</tr>
</table> 

CDMA-based devices must report signal strength based on compensated RSSI (accounts for noise) and not
     based on raw RSSI.


### -field ErrorRate

A coded value that represents a percentage range of error rates. For GSM-based devices, use the
     values from the Channel bit error rate column in the following table. For CDMA-based devices, use the
     values from the Frame error rate column. For both cases, use WWAN_ERROR_RATE_UNKNOWN to denote an
     unknown error rate.
     
<table>
<tr>
<th>Channel bit error rate (in %)</th>
<th>Frame error rate (in %)</th>
<th>Coded value (Min=0, Max=7)</th>
</tr>
<tr>
<td>
&lt; 0.2

</td>
<td>
&lt; 0.01

</td>
<td>
0

</td>
</tr>
<tr>
<td>
0.2-0.4

</td>
<td>
0.01-0.1

</td>
<td>
1

</td>
</tr>
<tr>
<td>
0.4-0.8

</td>
<td>
0.1-0.5

</td>
<td>
2

</td>
</tr>
<tr>
<td>
0.8-1.6

</td>
<td>
0.5-1.0

</td>
<td>
3

</td>
</tr>
<tr>
<td>
- 3.2

</td>
<td>
1.0 - -2.0

</td>
<td>
4

</td>
</tr>
<tr>
<td>
- 6.4

</td>
<td>
2.0-4.0

</td>
<td>
5

</td>
</tr>
<tr>
<td>
6.4-12.8

</td>
<td>
4.0-8.0

</td>
<td>
6

</td>
</tr>
<tr>
<td>
&gt; 12.8

</td>
<td>
&gt; 8.0

</td>
<td>
7

</td>
</tr>
<tr>
<td colspan="2">
Unknown or undetectable

</td>
<td>
WWAN_ERROR_RATE_UNKNOWN

</td>
</tr>
</table> 


### -field RssiInterval

The current interval, in seconds, at which the miniport driver has been set to (or the default
     interval, if one has not been set), that the miniport driver will provide updates about the signal
     state. Specify WWAN_RSSI_DISABLE to indicate that the miniport driver does not implement interval-based
     reporting. Miniport drivers should populate this member with the interval in response to an earlier
     request from the MB Service for WWAN_RSSI_DEFAULT.


### -field RssiThreshold

The current threshold, in threshold units, at which the miniport driver has been set to (or the
     default interval, if one has not been set), that the miniport driver will provide updates about the
     signal state. Specify WWAN_RSSI_DISABLE to indicate that the miniport driver does not implement
     threshold-based reporting. Miniport drivers should populate this member with the threshold units in
     response to an earlier request from the MB Service for WWAN_RSSI_DEFAULT.


## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_signal_state.md">NDIS_WWAN_SIGNAL_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SIGNAL_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

