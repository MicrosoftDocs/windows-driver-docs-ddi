---
UID: NS:wlclient._DOT11_BSS_LIST
title: "_DOT11_BSS_LIST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_list.htm
old-project: netvista
ms.assetid: e5c31c4d-8c46-4af1-90de-0311cc90c6c0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_BSS_LIST, ,, 1, B, D, DOT11_BSS_LIST, DOT11_BSS_LIST structure [Network Drivers Starting with Windows Vista], I, L, Native_802.11_data_types_9b32efe4-bc69-4e6b-9475-449a77c110da.xml, O, P, PDOT11_BSS_LIST, PDOT11_BSS_LIST structure pointer [Network Drivers Starting with Windows Vista], S, T, _, _DOT11_BSS_LIST, netvista.dot11_bss_list, wlclient/DOT11_BSS_LIST, wlclient/PDOT11_BSS_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlclient.h
req.include-header: Wlclient.h
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
-	wlclient.h
apiname:
-	DOT11_BSS_LIST
product: Windows
targetos: Windows
req.typenames: DOT11_BSS_LIST, *PDOT11_BSS_LIST
req.product: Windows 10 or later.
---

# _DOT11_BSS_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_BSS_LIST structure identifies a list of one or more IEEE 802.11 Beacon and Probe Response
  frames.


## -syntax


````
typedef struct _DOT11_BSS_LIST {
  ULONG  uNumOfBytes;
  PUCHAR pucBuffer;
} DOT11_BSS_LIST, *PDOT11_BSS_LIST;
````


## -struct-fields




### -field uNumOfBytes

The length, in bytes, of the data within the buffer referenced by the 
     <b>pucBuffer</b> member.


### -field pucBuffer

A pointer to a buffer that contains a list of 
     <a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a> structures. Each
     DOT11_BSS_ENTRY structure specifies a single 802.11 Beacon and Probe Response frame.
     

The DOT11_BSS_ENTRY structure has a variable length. However, each entry within the list of
     DOT11_BSS_ENTRY structures does not contain padding for the alignment of the next entry in the
     list.


## -remarks



The 802.11 Beacon and Probe Response frames within the 
    <b>pucBuffer</b> member were received from the underlying 802.11 station during its previous scan
    operation. For more information about this operation, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan
    Operations</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
   Dot11ExtIhvPerformCapabilityMatch</a>



<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_BSS_LIST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

