---
UID: NS:windot11._DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
title: "_DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_frequency_adopted_parameters.htm
old-project: netvista
ms.assetid: c6f98202-b70e-4ef7-853a-b97bb5e6294e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11_phy_frequency_adopted_parameters, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_7043b8b8-3b99-4350-bcb5-4ea194c7fd9d.xml, _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, windot11/PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, windot11/DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS"
req.product: Windows 10 or later.
---

# _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure specifies the channel or frequency that the
  802.11 station has adopted to communicate with a peer station on an infrastructure BSS.


## -syntax


````
typedef struct _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulPhyId;
  union {
    ULONG ulChannel;
    ULONG ulFrequency;
  };
} DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS;
````


## -struct-fields




#### - ulChannel

The channel number of the 
      <mshelp:link keywords="netvista.dsss__hrdsss__and_erp_phy_configuration" tabindex="0">DSSS, HRDSSS, and ERP PHY
      configurations</mshelp:link> that the NIC has adopted to communicate over the BSS network.


#### - ulFrequency

The orthogonal frequency division multiplexing (OFDM) frequency that the NIC has adopted to
      communicate over the BSS network.


#### - Header

The type, revision, and size of the DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure. This member
     is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


#### Revision

This member must be set to DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS_REVISION_1.


#### Size

This member must be set to 
       <b>sizeof</b>(DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS).


#### - ulPhyId

The value of an entry in the list of active PHY types defined by the 
     <b>msDot11ActivePhyList</b> MIB object that specifies the current channel or frequency that the NIC has
     adopted to communicate over the BSS network.
     

The miniport driver sets 
     <b>msDot11ActivePhyList</b> object to the list of PHYs that have been activated for use over the current
     BSS network connection. For more information about the 
     <b>msDot11ActivePhyList</b> MIB object, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>.

This member should not be set to DOT11_PHY_ID_ANY.


## -remarks


The Native 802.11 miniport driver includes a DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure when the
    driver makes an 
    <mshelp:link keywords="netvista.ndis_status_dot11_phy_frequency_adopted" tabindex="0">
    NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</mshelp:link> status indication.



## -see-also

<mshelp:link keywords="netvista.ndis_status_dot11_phy_frequency_adopted" tabindex="0">
   NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

