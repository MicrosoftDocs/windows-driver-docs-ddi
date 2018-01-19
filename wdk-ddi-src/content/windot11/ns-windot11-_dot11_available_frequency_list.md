---
UID: NS:windot11._DOT11_AVAILABLE_FREQUENCY_LIST
title: _DOT11_AVAILABLE_FREQUENCY_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_available_frequency_list.htm
old-project: netvista
ms.assetid: b8862ba3-c871-4d9b-9ee4-99ec9d0bcda9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_AVAILABLE_FREQUENCY_LIST, *PDOT11_AVAILABLE_FREQUENCY_LIST, DOT11_AVAILABLE_FREQUENCY_LIST
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
req.alt-api: DOT11_AVAILABLE_FREQUENCY_LIST
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
req.typenames: *PDOT11_AVAILABLE_FREQUENCY_LIST, DOT11_AVAILABLE_FREQUENCY_LIST
req.product: Windows 10 or later.
---

# _DOT11_AVAILABLE_FREQUENCY_LIST structure



## -description

## -syntax

````
typedef struct _DOT11_AVAILABLE_FREQUENCY_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              uFrequencyValue[1];
} DOT11_AVAILABLE_FREQUENCY_LIST, *PDOT11_AVAILABLE_FREQUENCY_LIST;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_AVAILABLE_FREQUENCY_LIST structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_AVAILABLE_FREQUENCY_LIST_REVISION_1.


### -field Size

This member must be set to
       <b>sizeof</b>(DOT11_AVAILABLE_FREQUENCY_LIST).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfEntries

The number of entries in the 
     <b>uFrequencyValue</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>uFrequencyValue</b> array can contain.


### -field uFrequencyValue

An array that specifies the list of available frequencies that the NIC can operate with.


## -remarks
This structure is used with 
    <a href="netvista.oid_dot11_available_frequency_list">
    OID_DOT11_AVAILABLE_FREQUENCY_LIST</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.oid_dot11_available_frequency_list">
   OID_DOT11_AVAILABLE_FREQUENCY_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_AVAILABLE_FREQUENCY_LIST structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

