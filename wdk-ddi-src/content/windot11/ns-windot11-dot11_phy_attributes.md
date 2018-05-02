---
UID: NS:windot11.DOT11_PHY_ATTRIBUTES
title: DOT11_PHY_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_attributes.htm
old-project: netvista
ms.assetid: 9e81144e-e562-4f61-83de-7b7659106de8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_PHY_ATTRIBUTES, DOT11_PHY_ATTRIBUTES, DOT11_PHY_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_76ba44f0-4597-4397-b686-1f70e5e27eec.xml, PDOT11_PHY_ATTRIBUTES, PDOT11_PHY_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_phy_attributes, windot11/DOT11_PHY_ATTRIBUTES, windot11/PDOT11_PHY_ATTRIBUTES"
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
-	DOT11_PHY_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES
req.product: Windows 10 or later.
---

# DOT11_PHY_ATTRIBUTES structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_ATTRIBUTES structure defines the physical and operating attributes of a PHY on the
  802.11 station.


## -syntax


````
typedef struct DOT11_PHY_ATTRIBUTES {
  NDIS_OBJECT_HEADER                  Header;
  DOT11_PHY_TYPE                      PhyType;
  BOOLEAN                             bHardwarePhyState;
  BOOLEAN                             bSoftwarePhyState;
  BOOLEAN                             bCFPollable;
  ULONG                               uMPDUMaxLength;
  DOT11_TEMP_TYPE                     TempType;
  DOT11_DIVERSITY_SUPPORT             DiversitySupport;
  union {
    DOT11_HRDSSS_PHY_ATTRIBUTES HRDSSSAttributes;
    DOT11_OFDM_PHY_ATTRIBUTES   OFDMAttributes;
    DOT11_ERP_PHY_ATTRIBUTES    ERPAttributes;
  };
  ULONG                               uNumberSupportedPowerLevels;
  ULONG                               TxPowerLevels[8];
  ULONG                               uNumDataRateMappingEntries;
  DOT11_DATA_RATE_MAPPING_ENTRY       DataRateMappingEntries[DOT11_RATE_SET_MAX_LENGTH];
  DOT11_SUPPORTED_DATA_RATES_VALUE_V2 SupportedDataRatesValue;
} DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_PHY_ATTRIBUTES structure. This member is formatted as an 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of 
      <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_PHY_ATTRIBUTES_REVISION_1.



#### Size

This member must be set to 
        sizeof(DOT11_PHY_ATTRIBUTES).

For more information about these members, see 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PhyType

The type of the PHY as specified by a 
     <a href="..\windot11\ne-windot11-_dot11_phy_type.md">DOT11_PHY_TYPE</a> enumerator value.


### -field bHardwarePhyState

A Boolean value that specifies the hardware power state of the PHY. If <b>TRUE</b>, the hardware power
      state is enabled. If <b>FALSE</b>, the hardware power state is disabled.

For more information about the PHY's hardware power state, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-hardware-phy-state">
      OID_DOT11_HARDWARE_PHY_STATE</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's hardware power state changes, the miniport driver must make an 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-phy-state-changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div>
<div> </div>

### -field bSoftwarePhyState

A Boolean value that specifies the software power state of the PHY. If <b>TRUE</b>, the software power
      state is enabled. If <b>FALSE</b>, the software power state is disabled.

For more information about the PHY's software power state, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-phy-state-changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div>
<div> </div>

### -field bCFPollable

A Boolean value that, if set to <b>TRUE</b>, indicates that the 802.11 station supports CF-Poll frames. For
      more information about CF-Poll frames, refer to Clause 9.4 of the IEEE 802.11-2012 standard.

This member is not applicable to the Extensible Access Point (ExtAP) operation mode and is ignored
      when the NIC is in the ExtAP mode.


### -field uMPDUMaxLength

The maximum length, in bytes, of a media access control (MAC) protocol data unit (MPDU) frame that
      the PHY can transmit or receive. For more information, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569387">OID_DOT11_MPDU_MAX_LENGTH</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an
      NDIS_STATUS_DOT11_MPDU_MAX_LENGTH_CHANGED media-specific status indication.</div>
<div> </div>

### -field TempType

The PHY's operating temperature range, defined through a 
      <a href="..\windot11\ne-windot11-_dot11_temp_type.md">DOT11_TEMP_TYPE</a> enumeration value.


### -field DiversitySupport

The PHY's type of antenna diversity, defined through a 
      <a href="..\windot11\ne-windot11-_dot11_diversity_support.md">DOT11_DIVERSITY_SUPPORT</a> enumeration
      value.


### -field PhySpecificAttributes

 




#### - DataRateMappingEntries

An array of the data rates supported by the PHY. Each entry is formatted as a 
      <a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">
      DOT11_DATA_RATE_MAPPING_ENTRY</a> structure.


#### - ERPAttributes

The PHY-specific attributes of an extended-rate PHY (ERP) type. The miniport driver must use this
       member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_erp.


#### - HRDSSSAttributes

The PHY-specific attributes of a high-rate direct-sequence spread spectrum (HRDSS) PHY type. The
       miniport driver must use this member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_hrdsss.


#### - OFDMAttributes

The PHY-specific attributes of an orthogonal frequency division multiplexing (OFDM) PHY type. The
       miniport driver must use this member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_ofdm.


#### - SupportedDataRatesValue

An array of the following data rates supported by the PHY:

<ul>
<li>
The transmit data rates supported by the Physical Layer Convergence Procedure (PLCP) and Physical
        Media Dependent (PMD) sublayer of the PHY.

</li>
<li>
The receive data rates supported by the PLCP and PMD of the PHY.

</li>
</ul>
Each entry in the array is formatted as a DOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure.


#### - TxPowerLevels

An array of the supported transmit power levels in units of milliwatts (mWs). Each power level must
      be a value from 0 through 1000.


#### - uNumDataRateMappingEntries

The number of data rates within the 
      <b>DataRateMappingEntries</b> array.


#### - uNumberSupportedPowerLevels

The number of power levels within the 
      <b>TxPowerLevels</b> array. 
      <b>uNumOfSupportedPowerLevels</b> must have a value from 1 through 8.


## -remarks



The 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure contains a member (<b>pExtPhyAttributes</b>) that specifies the address of an array of DOT11_PHY_ATTRIBUTES structures. When
    the miniport driver calls 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>,
    the driver sets the 
    <i>MiniportAttributes</i> parameter to the address of driver-allocated block of memory which contains an
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the array of DOT11_PHY_ATTRIBUTES
    structure.




## -see-also

<a href="..\windot11\ne-windot11-_dot11_diversity_support.md">DOT11_DIVERSITY_SUPPORT</a>



<a href="..\windot11\ne-windot11-_dot11_phy_type.md">DOT11_PHY_TYPE</a>



<a href="..\windot11\ns-windot11-dot11_ofdm_phy_attributes.md">DOT11_OFDM_PHY_ATTRIBUTES</a>



<a href="..\windot11\ns-windot11-_dot11_supported_data_rates_value_v2.md">
   DOT11_SUPPORTED_DATA_RATES_VALUE_V2</a>



<a href="..\windot11\ns-windot11-dot11_erp_phy_attributes.md">DOT11_ERP_PHY_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-hardware-phy-state">OID_DOT11_HARDWARE_PHY_STATE</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="..\windot11\ne-windot11-_dot11_temp_type.md">DOT11_TEMP_TYPE</a>



<a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">DOT11_DATA_RATE_MAPPING_ENTRY</a>



<a href="..\windot11\ns-windot11-dot11_hrdsss_phy_attributes.md">DOT11_HRDSSS_PHY_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


