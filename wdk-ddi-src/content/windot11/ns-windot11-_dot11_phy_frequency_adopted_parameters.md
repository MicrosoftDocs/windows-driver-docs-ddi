---
UID: NS:windot11._DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
title: _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_frequency_adopted_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure"]
ms.keywords: "*PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_7043b8b8-3b99-4350-bcb5-4ea194c7fd9d.xml, PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, netvista.dot11_phy_frequency_adopted_parameters, windot11/DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, windot11/PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
targetos: Windows
req.typenames: DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
f1_keywords:
 - _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
 - windot11/_DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
 - PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
 - windot11/PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
 - DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
 - windot11/DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
product:
 - Windows 10 or later.
---

# _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure specifies the channel or frequency that the
  802.11 station has adopted to communicate with a peer station on an infrastructure BSS.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure. This member
     is formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field ulPhyId

The value of an entry in the list of active PHY types defined by the
     <b>msDot11ActivePhyList</b> MIB object that specifies the current channel or frequency that the NIC has
     adopted to communicate over the BSS network.


The miniport driver sets
     <b>msDot11ActivePhyList</b> object to the list of PHYs that have been activated for use over the current
     BSS network connection. For more information about the
     <b>msDot11ActivePhyList</b> MIB object, see
     <a href="/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>.

This member should not be set to DOT11_PHY_ID_ANY.


#### - ulChannel

The channel number of the
      <a href="/windows-hardware/drivers/network/dsss--hrdsss--and-erp-phy-configuration">DSSS, HRDSSS, and ERP PHY
      configurations</a> that the NIC has adopted to communicate over the BSS network.


#### - ulFrequency

The orthogonal frequency division multiplexing (OFDM) frequency that the NIC has adopted to
      communicate over the BSS network.

## -syntax

```cpp
typedef struct _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulPhyId;
  union {
    ULONG ulChannel;
    ULONG ulFrequency;
  };
} DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS;
```

## -remarks

The Native 802.11 miniport driver includes a DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure when the
    driver makes an
    <a href="/windows-hardware/drivers/network/ndis-status-dot11-phy-frequency-adopted">
    NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</a> status indication.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-phy-frequency-adopted">
   NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
