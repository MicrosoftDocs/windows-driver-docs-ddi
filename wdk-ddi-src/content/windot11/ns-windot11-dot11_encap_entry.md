---
UID: NS:windot11.DOT11_ENCAP_ENTRY
title: DOT11_ENCAP_ENTRY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_encap_entry.htm
old-project: netvista
ms.assetid: d17547c5-47a3-4d10-b27f-6a3bbf7aad03
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11_encap_entry, PDOT11_ENCAP_ENTRY structure pointer [Network Drivers Starting with Windows Vista], Native_802.11_data_types_3304c37a-c08f-488e-a75d-d31d59a4a491.xml, *PDOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY, PDOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY structure [Network Drivers Starting with Windows Vista], windot11/DOT11_ENCAP_ENTRY, windot11/PDOT11_ENCAP_ENTRY
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
-	DOT11_ENCAP_ENTRY
product: Windows
targetos: Windows
req.typenames: DOT11_ENCAP_ENTRY, *PDOT11_ENCAP_ENTRY
req.product: Windows 10 or later.
---

# DOT11_ENCAP_ENTRY structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ENCAP_ENTRY structure defines an encapsulation type to be applied to the payload of an
  802.11 packet based on the packet's IEEE EtherType.


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
     




##### - usEncapType.DOT11_ENCAP_RFC_1042

The encapsulation that is defined through IETF RFC 1042.


##### - usEncapType.DOT11_ENCAP_802_IH

The encapsulation that is defined through the IEEE 802.1h-1997 standard.


## -remarks


The miniport driver returns an encapsulation list when it makes an 
    <mshelp:link keywords="netvista.ndis_status_dot11_association_completion" tabindex="0">
    NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</mshelp:link> indication. The encapsulation list specified in the
    indication applies to the association with an access point (AP) in an infrastructure basic service set
    (BSS) network.
<div class="alert"><b>Note</b>  The miniport driver cannot return an encapsulation list when associating with peer
    stations within an independent BSS network.</div><div> </div>For more information about 802.11 packet payload encapsulation, see 
    <a href="https://technet.microsoft.com/en-us/library/cc757419">802.11 Payload Encapsulation</a>.



## -see-also

<mshelp:link keywords="netvista.ndis_status_dot11_association_completion" tabindex="0">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</mshelp:link>

<mshelp:link keywords="netvista.dot11_association_completion_parameters" tabindex="0"><b>
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ENCAP_ENTRY structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

