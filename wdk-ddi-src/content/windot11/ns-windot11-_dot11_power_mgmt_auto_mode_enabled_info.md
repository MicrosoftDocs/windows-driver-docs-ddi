---
UID: NS:windot11._DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO
title: "_DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO" (windot11.h)
description: The DOT11_POWER_MGMT_AUTO_MODE_ENABLED structure describes to a device whether to automatically manage its power saving mode.
old-location: netvista\dot11_power_mgmt_auto_mode_enabled_info.htm
tech.root: netvista
ms.assetid: 9C75544F-A14C-4741-91FC-434AE1872A6E
ms.date: 02/16/2018
ms.keywords: "*PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO structure [Network Drivers Starting with Windows Vista], PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO structure pointer [Network Drivers Starting with Windows Vista], _DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, netvista.dot11_power_mgmt_auto_mode_enabled_info, windot11/DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, windot11/PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Windot11.h
api_name:
-	DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO
product:
- Windows
targetos: Windows
req.typenames: DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, *PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO
product:
- Windows 10 or later.
---

# _DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_POWER_MGMT_AUTO_MODE_ENABLED structure describes to a device whether to automatically manage its power saving mode.


## -syntax


```cpp
typedef struct _DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO {
  NDIS_OBJECT_HEADER Header;
  BOOLEAN            bEnabled;
} DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO, *PDOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_POWER_MGMT_AUTO_MODE_ENABLED_INFO structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_POWER_MGMT_AUTO_MODE_ENABLED_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_POWER_MGMT_AUTO_MODE_ENABLE_INFO_REVISION_1</td>
</tr>
</table>
 


### -field bEnabled

Windows sets this member to TRUE to indicate to the device to automatically manage its power saving mode. Windows set this to FALSE to indicate to the device to stop automatically managing its power save mode.


## -remarks



When Windows sets the device to auto power saving mode, devices must remain in this mode until Windows issues another request with <b>bEnabled</b> set to FALSE. In auto power saving mode, Windows may issue a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-power-mgmt-request">OID_DOT11_POWER_MGMT_REQUEST</a><i>set</i> request that hardware can use as a hint to adjust its power management.



