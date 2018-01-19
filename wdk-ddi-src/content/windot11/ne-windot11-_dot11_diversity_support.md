---
UID: NE:windot11._DOT11_DIVERSITY_SUPPORT
title: _DOT11_DIVERSITY_SUPPORT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_diversity_support.htm
old-project: netvista
ms.assetid: 64eeb1bf-c18a-4dfa-b6ea-438d9e10fe4a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_DIVERSITY_SUPPORT, *PDOT11_DIVERSITY_SUPPORT, DOT11_DIVERSITY_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_DIVERSITY_SUPPORT
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
req.typenames: *PDOT11_DIVERSITY_SUPPORT, DOT11_DIVERSITY_SUPPORT
req.product: Windows 10 or later.
---

# _DOT11_DIVERSITY_SUPPORT enumeration



## -description

## -syntax

````
typedef enum _DOT11_DIVERSITY_SUPPORT { 
  dot11_diversity_support_unknown       = 0,
  dot11_diversity_support_fixedlist     = 1,
  dot11_diversity_support_notsupported  = 2,
  dot11_diversity_support_dynamic       = 3
} DOT11_DIVERSITY_SUPPORT, *PDOT11_DIVERSITY_SUPPORT;
````


## -enum-fields

### -field dot11_diversity_support_unknown

An uninitialized or unknown diversity support type.


### -field dot11_diversity_support_fixedlist

The PHY supports antenna diversity that is performed over the fixed list of antennas defined in
     the 
     <b>dot11DiversitySelectionRx</b> MIB object. For more information about this MIB object, see 
     <a href="netvista.oid_dot11_diversity_selection_rx">
     OID_DOT11_DIVERSITY_SELECTION_RX</a>.


### -field dot11_diversity_support_notsupported

The PHY does not support antenna diversity.


### -field dot11_diversity_support_dynamic

The PHY supports antenna diversity and the dynamic control of diversity. The PHY layer management
     entity (LME) can dynamically modify the list of antennas specified by the 
     <b>dot11DiversitySelectionRx</b> MIB object


## -remarks


## -see-also
<dl>
<dt>
<a href="netvista.oid_dot11_diversity_selection_rx">
   OID_DOT11_DIVERSITY_SELECTION_RX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_DIVERSITY_SUPPORT enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

