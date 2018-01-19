---
UID: NS:windot11._DOT11_SUPPORTED_ANTENNA
title: _DOT11_SUPPORTED_ANTENNA
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_antenna.htm
old-project: netvista
ms.assetid: 55a9c9e0-24e2-436f-9132-77ae1bab7c2c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_SUPPORTED_ANTENNA, DOT11_SUPPORTED_ANTENNA, *PDOT11_SUPPORTED_ANTENNA
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
req.alt-api: DOT11_SUPPORTED_ANTENNA
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
req.typenames: DOT11_SUPPORTED_ANTENNA, *PDOT11_SUPPORTED_ANTENNA
req.product: Windows 10 or later.
---

# _DOT11_SUPPORTED_ANTENNA structure



## -description

## -syntax

````
typedef struct _DOT11_SUPPORTED_ANTENNA {
  ULONG   uAntennaListIndex;
  BOOLEAN bSupportedAntenna;
} DOT11_SUPPORTED_ANTENNA, *PDOT11_SUPPORTED_ANTENNA;
````


## -struct-fields

### -field uAntennaListIndex

A value, from 1 through 255, that uniquely identifies the antenna.


### -field bSupportedAntenna

A Boolean value that indicates, if <b>TRUE</b>, that the antenna referenced by the 
     <b>uAntennaListIndex</b> value supports transmit and receive operations.


## -remarks
The meaning of the 
    <b>bSupportedAntenna</b> member depends on the OID that it is used with. For example, if 
    <b>bSupportedAntenna</b> is <b>TRUE</b> when an antenna list is queried through 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569428">OID_DOT11_SUPPORTED_RX_ANTENNA</a>,
    the antenna referenced by the 
    <b>uAntennaListIndex</b> member is supported for receive operations.


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-_dot11_supported_antenna_list.md">DOT11_SUPPORTED_ANTENNA_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569428">OID_DOT11_SUPPORTED_RX_ANTENNA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569429">OID_DOT11_SUPPORTED_TX_ANTENNA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SUPPORTED_ANTENNA structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

