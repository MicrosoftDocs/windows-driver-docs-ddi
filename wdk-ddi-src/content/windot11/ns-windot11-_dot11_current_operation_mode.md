---
UID: NS:windot11._DOT11_CURRENT_OPERATION_MODE
title: _DOT11_CURRENT_OPERATION_MODE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_current_operation_mode.htm
old-project: netvista
ms.assetid: 085ee8f4-7e96-416a-a59f-f35c8ad0dbf4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
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
req.alt-api: DOT11_CURRENT_OPERATION_MODE
req.alt-loc: windot11.h
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
req.typenames: DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
req.product: Windows 10 or later.
---

# _DOT11_CURRENT_OPERATION_MODE structure



## -description

## -syntax

````
typedef struct _DOT11_CURRENT_OPERATION_MODE {
  ULONG uReserved;
  ULONG uCurrentOpMode;
} DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE;
````


## -struct-fields

### -field uReserved

This member is reserved. The miniport driver must not modify the value of this member.


### -field uCurrentOpMode

A bitmask of the miniport driver's current operation modes. This bitmask is defined through the
      following:




### -field DOT11_OPERATION_MODE_EXTENSIBLE_AP

Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation
         mode.

This value is available starting with Windows 7.


### -field DOT11_OPERATION_MODE_EXTENSIBLE_STATION

Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
        mode.


### -field DOT11_OPERATION_MODE_NETWORK_MONITOR

Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.


### -field DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode. This mode is available starting in Windows 8.


### -field DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.This mode is available starting in Windows 8.


### -field DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode. This mode is available starting in Windows 8.

</dd>
</dl>
For more information about operation modes, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
      Modes</a>.


## -remarks
The miniport driver must specify only one operation mode in the 
    <b>uCurrentOpMode</b> member.

For more information about Native 802.11 operation modes, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
    Modes</a>.


## -see-also
<dl>
<dt>
<a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a>
</dt>
<dt>
<a href="netvista.oid_dot11_current_operation_mode">
   OID_DOT11_CURRENT_OPERATION_MODE</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation Modes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CURRENT_OPERATION_MODE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

