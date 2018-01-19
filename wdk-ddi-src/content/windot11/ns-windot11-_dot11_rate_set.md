---
UID: NS:windot11._DOT11_RATE_SET
title: _DOT11_RATE_SET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_rate_set.htm
old-project: netvista
ms.assetid: 943ae1dc-cc42-4d6d-b2fb-9af25505e561
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_RATE_SET, *PDOT11_RATE_SET, DOT11_RATE_SET
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
req.alt-api: DOT11_RATE_SET
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
req.typenames: *PDOT11_RATE_SET, DOT11_RATE_SET
req.product: Windows 10 or later.
---

# _DOT11_RATE_SET structure



## -description

## -syntax

````
typedef struct _DOT11_RATE_SET {
  ULONG uRateSetLength;
  UCHAR ucRateSet[DOT11_RATE_SET_MAX_LENGTH];
} DOT11_RATE_SET, *PDOT11_RATE_SET;
````


## -struct-fields

### -field uRateSetLength

The number of entries in the 
     <b>ucRateSet</b> array.


### -field ucRateSet

The set of data rates.


## -remarks
The values that are specified in the 
    <b>ucRateSet</b> array define the data rates at which the 802.11 station may transmit and receive data.
    Each value is an index into the table of data rates that are returned by the driver for a query of 
    <a href="netvista.oid_dot11_data_rate_mapping_table">
    OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>.


## -see-also
<dl>
<dt>
<a href="netvista.oid_dot11_data_rate_mapping_table">
   OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569395">OID_DOT11_OPERATIONAL_RATE_SET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_RATE_SET structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

