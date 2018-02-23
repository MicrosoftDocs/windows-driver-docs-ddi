---
UID: NS:windot11.DOT11_PRIVACY_EXEMPTION
title: DOT11_PRIVACY_EXEMPTION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_privacy_exemption.htm
old-project: netvista
ms.assetid: ee4499d0-3275-419d-9ab2-89edd77e0374
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: windot11/DOT11_PRIVACY_EXEMPTION, *PDOT11_PRIVACY_EXEMPTION, windot11/PDOT11_PRIVACY_EXEMPTION, DOT11_PRIVACY_EXEMPTION structure [Network Drivers Starting with Windows Vista], DOT11_PRIVACY_EXEMPTION, PDOT11_PRIVACY_EXEMPTION structure pointer [Network Drivers Starting with Windows Vista], Native_802.11_data_types_8dd63374-57b1-4dc8-9dca-76dcc5ade9fd.xml, netvista.dot11_privacy_exemption, PDOT11_PRIVACY_EXEMPTION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_PRIVACY_EXEMPTION
product: Windows
targetos: Windows
req.typenames: DOT11_PRIVACY_EXEMPTION, *PDOT11_PRIVACY_EXEMPTION
req.product: Windows 10 or later.
---

# DOT11_PRIVACY_EXEMPTION structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PRIVACY_EXEMPTION structure defines a decryption exemption for a specified network
  EtherType.


## -syntax


````
typedef struct DOT11_PRIVACY_EXEMPTION {
  USHORT usEtherType;
  USHORT usExemptionActionType;
  USHORT usExemptionPacketType;
} DOT11_PRIVACY_EXEMPTION, *PDOT11_PRIVACY_EXEMPTION;
````


## -struct-fields




### -field usEtherType

The value of the IEEE EtherType in big-endian byte order.


### -field usExemptionActionType

The type of exemption for the specified EtherType. The following exemption types are defined:
     





#### DOT11_EXEMPT_ALWAYS

The 802.11 station must discard the received packet if the Protected Frame subfield of the Frame
       Control field in the 802.11 MAC header is set to one.



#### DOT11_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE

The 802.11 station must discard the received packet if a key-mapping key for the source MAC
       address is available and the Protected Frame subfield of the Frame Control field in the 802.11 MAC
       header is set to zero.


### -field usExemptionPacketType

The type of packet that the exemption for the specified EtherType applies to. The following packet
     types are defined:
     





#### DOT11_EXEMPT_UNICAST

Exempt only unicast packets.



#### DOT11_EXEMPT_MULTICAST

Exempt only multicast or broadcast packets.



#### DOT11_EXEMPT_BOTH

Exempt all packet types.


## -remarks



The 802.11 station's packet exemption list if configured through a set request of 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-privacy-exemption-list">
    OID_DOT11_PRIVACY_EXEMPTION_LIST</a>. For each packet the 802.11 station receives, it will apply the
    decryption exemption specified by the list entry with a 
    <b>usEtherType</b> value that matches the EtherType of the packet.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-privacy-exemption-list">
   OID_DOT11_PRIVACY_EXEMPTION_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PRIVACY_EXEMPTION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

