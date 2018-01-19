---
UID: NS:windot11._DOT11_VWIFI_COMBINATION
title: _DOT11_VWIFI_COMBINATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_vwifi_combination.htm
old-project: netvista
ms.assetid: 05be98a8-dad2-4539-b725-e898db19a789
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_VWIFI_COMBINATION, *PDOT11_VWIFI_COMBINATION, DOT11_VWIFI_COMBINATION
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
req.alt-api: DOT11_VWIFI_COMBINATION
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
req.typenames: *PDOT11_VWIFI_COMBINATION, DOT11_VWIFI_COMBINATION
req.product: Windows 10 or later.
---

# _DOT11_VWIFI_COMBINATION structure



## -description

## -syntax

````
typedef struct _DOT11_VWIFI_COMBINATION {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumInfrastructure;
  ULONG              uNumAdhoc;
  ULONG              uNumSoftAP;
} DOT11_VWIFI_COMBINATION, *PDOT11_VWIFI_COMBINATION;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_VWIFI_COMBINATION structure. This member is formatted as
     an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_VWIFI_COMBINATION_REVISION_1.


### -field Size

This member must be set to 
       sizeof(DOT11_VWIFI_COMBINATION).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumInfrastructure

The number of 802.11 infrastructure stations supported. For more information, see the following
     Remarks section.


### -field uNumAdhoc

The number of Adhoc Stations supported. For more information, see the following Remarks
     section.


### -field uNumSoftAP

The number of Soft AP Stations supported. For more information, see the following Remarks
     section.


## -remarks
Starting with Windows 7, the 802.11 miniport driver must only report one or more of the following
    combination of member values.

<b>uNumInfrastructure</b> = 1

<b>uNumAdhoc</b> = 0

<b>uNumSoftAP</b> = 1


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_VWIFI_COMBINATION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

