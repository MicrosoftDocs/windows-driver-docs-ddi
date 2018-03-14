---
UID: NS:windot11._DOT11_RATE_SET
title: "_DOT11_RATE_SET"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_rate_set.htm
old-project: netvista
ms.assetid: 943ae1dc-cc42-4d6d-b2fb-9af25505e561
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_RATE_SET, DOT11_RATE_SET, DOT11_RATE_SET structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b2c617a6-b974-4b67-9f33-2ff5a99b55e9.xml, PDOT11_RATE_SET, PDOT11_RATE_SET structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RATE_SET, netvista.dot11_rate_set, windot11/DOT11_RATE_SET, windot11/PDOT11_RATE_SET"
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
-	DOT11_RATE_SET
product: Windows
targetos: Windows
req.typenames: DOT11_RATE_SET, *PDOT11_RATE_SET
req.product: Windows 10 or later.
---

# _DOT11_RATE_SET structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_RATE_SET structure defines the set of data rates that the 802.11 station supports.


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
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
    OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
   OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569395">OID_DOT11_OPERATIONAL_RATE_SET</a>



 

 


