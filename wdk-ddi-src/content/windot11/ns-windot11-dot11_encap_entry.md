---
UID: NS:windot11.DOT11_ENCAP_ENTRY
title: DOT11_ENCAP_ENTRY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_encap_entry.htm
old-project: netvista
ms.assetid: d17547c5-47a3-4d10-b27f-6a3bbf7aad03
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_ENCAP_ENTRY, *PDOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY
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
req.alt-api: DOT11_ENCAP_ENTRY
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
req.typenames: *PDOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY
req.product: Windows 10 or later.
---

# DOT11_ENCAP_ENTRY structure



## -description

## -syntax

````
typedef struct DOT11_ENCAP_ENTRY {
  USHORT usEtherType;
  USHORT usEncapType;
} DOT11_ENCAP_ENTRY, *PDOT11_ENCAP_ENTRY;
````


## -struct-fields

### -field usEtherType

The value of the IEEE EtherType in big-endian byte order. 
     

If the 
     <b>usEtherType</b> member is zero, the encapsulation that is specified by the 
     <b>usEncapType</b> member applies to all EtherType values. If the miniport driver sets 
     <b>usEtherType</b> to zero for an entry, it must be the only entry in the EtherType encapsulation
     list.


### -field usEncapType

The type of encapsulation that is performed on the EtherType specified by the 
     <b>usEtherType</b> member. The 
     <b>usEncapType</b> member can have one of the following values: 
     




### -field DOT11_ENCAP_RFC_1042

The encapsulation that is defined through IETF RFC 1042.


### -field DOT11_ENCAP_802_IH

The encapsulation that is defined through the IEEE 802.1h-1997 standard.

</dd>
</dl>

## -remarks
The miniport driver returns an encapsulation list when it makes an 
    <a href="netvista.ndis_status_dot11_association_completion">
    NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> indication. The encapsulation list specified in the
    indication applies to the association with an access point (AP) in an infrastructure basic service set
    (BSS) network.

For more information about 802.11 packet payload encapsulation, see 
    <a href="https://msdn.microsoft.com/03336b87-22b0-4a2a-aaa9-91c58f329a16">802.11 Payload Encapsulation</a>.


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_association_completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ENCAP_ENTRY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

