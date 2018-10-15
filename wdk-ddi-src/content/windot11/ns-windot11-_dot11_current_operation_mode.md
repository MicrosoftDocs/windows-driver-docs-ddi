---
UID: NS:windot11._DOT11_CURRENT_OPERATION_MODE
title: "_DOT11_CURRENT_OPERATION_MODE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_current_operation_mode.htm
tech.root: netvista
ms.assetid: 085ee8f4-7e96-416a-a59f-f35c8ad0dbf4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_d2f0f1a7-3e89-4ac1-acbd-a032909837a2.xml, PDOT11_CURRENT_OPERATION_MODE, PDOT11_CURRENT_OPERATION_MODE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_CURRENT_OPERATION_MODE, netvista.dot11_current_operation_mode, windot11/DOT11_CURRENT_OPERATION_MODE, windot11/PDOT11_CURRENT_OPERATION_MODE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	windot11.h
api_name:
-	DOT11_CURRENT_OPERATION_MODE
product:
- Windows
targetos: Windows
req.typenames: DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
product:
- Windows 10 or later.
---

# _DOT11_CURRENT_OPERATION_MODE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CURRENT_OPERATION_MODE structure defines the current Native 802.11 operation mode on the
  instance of a miniport driver that manages a wireless LAN (WLAN) adapter.


## -syntax


```
typedef struct _DOT11_CURRENT_OPERATION_MODE {
  ULONG uReserved;
  ULONG uCurrentOpMode;
} DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE;
```


## -struct-fields




### -field uReserved

This member is reserved. The miniport driver must not modify the value of this member.


### -field uCurrentOpMode

A bitmask of the miniport driver's current operation modes. This bitmask is defined through the
      following:





#### DOT11_OPERATION_MODE_EXTENSIBLE_AP

Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation
         mode.

This value is available starting with Windows 7.



#### DOT11_OPERATION_MODE_EXTENSIBLE_STATION

Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
        mode.



#### DOT11_OPERATION_MODE_NETWORK_MONITOR

Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.



#### DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode. This mode is available starting in Windows 8.



#### DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.This mode is available starting in Windows 8.



#### DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode. This mode is available starting in Windows 8.

For more information about operation modes, see
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
      Modes</a>.


## -remarks



The miniport driver must specify only one operation mode in the
    <b>uCurrentOpMode</b> member.

For more information about Native 802.11 operation modes, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
    Modes</a>.




## -see-also

<a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation Modes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-current-operation-mode">
   OID_DOT11_CURRENT_OPERATION_MODE</a>



 

 


