---
UID: NS:windot11._DOT11_SUPPORTED_DATA_RATES_VALUE_V2
title: "_DOT11_SUPPORTED_DATA_RATES_VALUE_V2"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_data_rates_value_v2.htm
old-project: netvista
ms.assetid: 2407204b-215c-481e-876d-740bc3d55ee3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_SUPPORTED_DATA_RATES_VALUE_V1, *PDOT11_SUPPORTED_DATA_RATES_VALUE_V2, DOT11_SUPPORTED_DATA_RATES_VALUE_V1, DOT11_SUPPORTED_DATA_RATES_VALUE_V2, DOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_20f2b1ba-9639-4a8b-b5c1-f7441300bea5.xml, PDOT11_SUPPORTED_DATA_RATES_VALUE_V2, PDOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_DATA_RATES_VALUE_V2, netvista.dot11_supported_data_rates_value_v2, windot11/DOT11_SUPPORTED_DATA_RATES_VALUE_V2, windot11/PDOT11_SUPPORTED_DATA_RATES_VALUE_V2"
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
-	DOT11_SUPPORTED_DATA_RATES_VALUE_V2
product: Windows
targetos: Windows
req.typenames: DOT11_SUPPORTED_DATA_RATES_VALUE_V2, *PDOT11_SUPPORTED_DATA_RATES_VALUE_V2
req.product: Windows 10 or later.
---

# _DOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure specifies a list of transmit and receive data rates
  for a PHY on the 802.11 station.


## -syntax


````
typedef struct _DOT11_SUPPORTED_DATA_RATES_VALUE_V2 {
  UCHAR ucSupportedTxDataRatesValue[MAX_NUM_SUPPORTED_RATES_V2];
  UCHAR ucSupportedRxDataRatesValue[MAX_NUM_SUPPORTED_RATES_V2];
} DOT11_SUPPORTED_DATA_RATES_VALUE_V2, *PDOT11_SUPPORTED_DATA_RATES_VALUE_V2;
````


## -struct-fields




### -field ucSupportedTxDataRatesValue

An array of the transmit data rates supported by the Physical Layer Convergence Procedure (PLCP)
     and Physical Media Dependent (PMD) sublayer of the PHY.


### -field ucSupportedRxDataRatesValue

An array of the receive data rates supported by the PLCP and PMD of the PHY.


## -remarks



Each entry in the 
    <b>ucSupportedTxDataRatesValue</b> and 
    <b>ucSupportedRxDataRatesValue</b> arrays must have a data rate index value as defined for the 
    <b>ucDataRateIndex</b> member of the 
    <a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">
    DOT11_DATA_RATE_MAPPING_ENTRY</a> structure. Each entry in these arrays must match a 
    <b>ucDataRateIndex</b> member from the table of data rates returned through a query of 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
    OID_DOT11_DATA_RATE_MAPPING_TABLE</a>. The index value must be between 2 and 127.

If the number of supported rates in either array is less than 255, the miniport driver must add an
    entry with a value of zero after the last data rate in the array. For example, if the 802.11 station
    supports only four transmit data rates, the miniport driver must set 
    <b>ucSupportedTxDataRatesValue[0..3]</b> with the four transmit rates and set 
    <b>ucSupportedTxDataRatesValue[4]</b> to zero.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">DOT11_DATA_RATE_MAPPING_ENTRY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
   OID_DOT11_DATA_RATE_MAPPING_TABLE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-data-rates-value">
   OID_DOT11_SUPPORTED_DATA_RATES_VALUE</a>



 

 


