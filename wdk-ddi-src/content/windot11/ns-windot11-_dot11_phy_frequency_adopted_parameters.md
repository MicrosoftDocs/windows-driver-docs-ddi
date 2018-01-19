---
UID: NS:windot11._DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
title: _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_frequency_adopted_parameters.htm
old-project: netvista
ms.assetid: c6f98202-b70e-4ef7-853a-b97bb5e6294e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
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
req.alt-api: DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
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
req.typenames: DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS, *PDOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure



## -description

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

### -field Header

The type, revision, and size of the DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure. This member
     is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS_REVISION_1.


### -field Size

This member must be set to 
       <b>sizeof</b>(DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS).

</dd>
</dl>
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569102">OID_DOT11_ACTIVE_PHY_LIST</a>.

This member should not be set to DOT11_PHY_ID_ANY.


### -field ulChannel

The channel number of the 
      <a href="netvista.dsss__hrdsss__and_erp_phy_configuration">DSSS, HRDSSS, and ERP PHY
      configurations</a> that the NIC has adopted to communicate over the BSS network.


### -field ulFrequency

The orthogonal frequency division multiplexing (OFDM) frequency that the NIC has adopted to
      communicate over the BSS network.


## -remarks
The Native 802.11 miniport driver includes a DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure when the
    driver makes an 
    <a href="netvista.ndis_status_dot11_phy_frequency_adopted">
    NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</a> status indication.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_phy_frequency_adopted">
   NDIS_STATUS_DOT11_PHY_FREQUENCY_ADOPTED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569102">OID_DOT11_ACTIVE_PHY_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_FREQUENCY_ADOPTED_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

