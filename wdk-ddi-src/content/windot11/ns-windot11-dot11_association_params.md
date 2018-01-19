---
UID: NS:windot11.DOT11_ASSOCIATION_PARAMS
title: DOT11_ASSOCIATION_PARAMS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_association_params.htm
old-project: netvista
ms.assetid: 74382195-ee1d-4b01-b882-2f357d801a25
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_ASSOCIATION_PARAMS, *PDOT11_ASSOCIATION_PARAMS, DOT11_ASSOCIATION_PARAMS
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
req.alt-api: DOT11_ASSOCIATION_PARAMS
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
req.typenames: *PDOT11_ASSOCIATION_PARAMS, DOT11_ASSOCIATION_PARAMS
req.product: Windows 10 or later.
---

# DOT11_ASSOCIATION_PARAMS structure



## -description

## -syntax

````
typedef struct DOT11_ASSOCIATION_PARAMS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  BSSID;
  ULONG              uAssocRequestIEsOffset;
  ULONG              uAssocRequestIEsLength;
} DOT11_ASSOCIATION_PARAMS, *PDOT11_ASSOCIATION_PARAMS;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_ASSOCIATION_PARAMS structure. This member is formatted
     as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_ASSOCIATION_PARAMS_REVISION_1.


### -field Size

This member must be set to 
       <b>sizeof</b>(DOT11_ASSOCIATION_PARAMS).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field BSSID

The basic service set (BSS) identifier (BSSID) of the infrastructure BSS network for which the
     association parameters are to be set.
     

The miniport driver should add new additional information elements (IEs) to an association request
     only if it is attempting to associate with an access point that has the matching BSSID.

If this member is set to the wildcard BSSID (0xFFFFFFFFFFFF), the miniport driver should add new
     additional information elements (IEs) to association requests for all access points that have valid
     BSSIDs.


### -field uAssocRequestIEsOffset

The offset of the additional IEs, in bytes, that the operating system requests be added to the
     association response. This offset is relative to the start of the buffer that contains the
     DOT11_ASSOCIATION_PARAMS structure. The default value is 0.


### -field uAssocRequestIEsLength

The length of the additional IEs, in bytes, that the operating system requests be added to the
     association response. The default value is 0.


## -remarks
This structure is used with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569104">OID_DOT11_ASSOCIATION_PARAMS</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569104">OID_DOT11_ASSOCIATION_PARAMS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ASSOCIATION_PARAMS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

