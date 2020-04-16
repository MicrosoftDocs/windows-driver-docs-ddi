---
UID: NS:windot11._DOT11_AVAILABLE_CHANNEL_LIST
title: _DOT11_AVAILABLE_CHANNEL_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_available_channel_list.htm
tech.root: netvista
ms.assetid: 11fee366-5853-4702-8179-d5b764174dce
ms.date: 02/16/2018
keywords: ["_DOT11_AVAILABLE_CHANNEL_LIST structure"]
ms.keywords: "*PDOT11_AVAILABLE_CHANNEL_LIST, DOT11_AVAILABLE_CHANNEL_LIST, DOT11_AVAILABLE_CHANNEL_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c36ff4d6-283a-484c-8d68-0109c6150f4f.xml, PDOT11_AVAILABLE_CHANNEL_LIST, PDOT11_AVAILABLE_CHANNEL_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_AVAILABLE_CHANNEL_LIST, netvista.dot11_available_channel_list, windot11/DOT11_AVAILABLE_CHANNEL_LIST, windot11/PDOT11_AVAILABLE_CHANNEL_LIST"
f1_keywords:
 - "windot11/DOT11_AVAILABLE_CHANNEL_LIST"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_AVAILABLE_CHANNEL_LIST
targetos: Windows
req.typenames: DOT11_AVAILABLE_CHANNEL_LIST, *PDOT11_AVAILABLE_CHANNEL_LIST
product:
- Windows 10 or later.
---

# _DOT11_AVAILABLE_CHANNEL_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AVAILABLE_CHANNEL_LIST structure specifies the available operating frequency channel list
  of the
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dsss--hrdsss--and-erp-phy-configuration">DSSS, HRDSSS, and ERP PHY
  configurations</a> that the NIC can operate with.


## -syntax


```cpp
typedef struct _DOT11_AVAILABLE_CHANNEL_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              uChannelNumber[1];
} DOT11_AVAILABLE_CHANNEL_LIST, *PDOT11_AVAILABLE_CHANNEL_LIST;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_AVAILABLE_CHANNEL_LIST structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_AVAILABLE_CHANNEL_LIST_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_AVAILABLE_CHANNEL_LIST).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfEntries

The number of entries in the
     <b>uChannelNumber</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>uChannelNumber</b> array can contain.


### -field uChannelNumber

An array that specifies the list of available operating frequency channels of the
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dsss--hrdsss--and-erp-phy-configuration">DSSS, HRDSSS, and ERP PHY
     configurations</a> that the NIC can operate with.


## -remarks



This structure is used with
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-available-channel-list">
    OID_DOT11_AVAILABLE_CHANNEL_LIST</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-available-channel-list">
   OID_DOT11_AVAILABLE_CHANNEL_LIST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


