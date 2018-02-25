---
UID: NS:windot11._DOT11_POWER_MGMT_MODE_STATUS_INFO
title: "_DOT11_POWER_MGMT_MODE_STATUS_INFO"
author: windows-driver-content
description: The DOT11_POWER_MGMT_MODE_STATUS_INFO structure describes the power mode of the hardware.
old-location: netvista\dot11_power_mgmt_mode_status_info.htm
old-project: netvista
ms.assetid: A373EA34-A7CF-47B3-8194-438BE7F4FC9C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_POWER_MGMT_MODE_STATUSINFO, ,, 1, A, D, DOT11_POWER_MGMT_MODE_STATUS_INFO, DOT11_POWER_MGMT_MODE_STATUS_INFO structure [Network Drivers Starting with Windows Vista], E, F, G, I, M, N, O, P, PDOT11_POWER_MGMT_MODE_STATUS_INFO, PDOT11_POWER_MGMT_MODE_STATUS_INFO structure pointer [Network Drivers Starting with Windows Vista], R, S, T, U, W, _, _DOT11_POWER_MGMT_MODE_STATUS_INFO, netvista.dot11_power_mgmt_mode_status_info, windot11/DOT11_POWER_MGMT_MODE_STATUS_INFO, windot11/PDOT11_POWER_MGMT_MODE_STATUS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
-	Windot11.h
apiname:
-	DOT11_POWER_MGMT_MODE_STATUS_INFO
product: Windows
targetos: Windows
req.typenames: DOT11_POWER_MGMT_MODE_STATUS_INFO, *PDOT11_POWER_MGMT_MODE_STATUSINFO
req.product: Windows 10 or later.
---

# _DOT11_POWER_MGMT_MODE_STATUS_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_POWER_MGMT_MODE_STATUS_INFO structure describes the power mode of the hardware.


## -syntax


````
typedef struct _DOT11_POWER_MGMT_MODE_STATUS_INFO {
  NDIS_OBJECT_HEADER      Header;
  DOT11_POWER_MODE        PowerSaveMode;
  ULONG                   uPowerSaveLevel;
  DOT11_POWER_MODE_REASON Reason;
} DOT11_POWER_MGMT_MODE_STATUS_INFO, *PDOT11_POWER_MGMT_MODE_STATUS_INFO;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_POWER_MGMT_MODE_STATUS_INFO structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_POWER_MGMT_MODE_STATUS_INFO_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_POWER_MGMT_MODE_STATUS_INFO_REVISION_1</td>
</tr>
</table>
 


### -field PowerSaveMode

The current power mode of the hardware. The mode may be <b>dot11_power_mode_active</b> or <b>dot11_power_mode_powersave</b>, but should not be <b>dot11_power_mode_unknown</b>.


### -field uPowerSaveLevel

One of the following values describing power saving levels:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>DOT11_POWER_SAVING_NO_POWER_SAVING</td>
<td>No power saving</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_FAST_PSP</td>
<td>Fast PSP</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_MAX_PSP</td>
<td>Maximum PSP</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_MAXIMUM_LEVEL</td>
<td>Maximum power saving level</td>
</tr>
</table>
 


### -field Reason

Reason that the device changed into the current power mode.


## -remarks



At each transition of the mode change, a device should remember the reason it made the last change.



