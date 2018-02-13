---
UID: NS:windot11._DOT11_AVAILABLE_CHANNEL_LIST
title: "_DOT11_AVAILABLE_CHANNEL_LIST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_available_channel_list.htm
old-project: netvista
ms.assetid: 11fee366-5853-4702-8179-d5b764174dce
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: windot11/PDOT11_AVAILABLE_CHANNEL_LIST, PDOT11_AVAILABLE_CHANNEL_LIST structure pointer [Network Drivers Starting with Windows Vista], DOT11_AVAILABLE_CHANNEL_LIST, PDOT11_AVAILABLE_CHANNEL_LIST, Native_802.11_data_types_c36ff4d6-283a-484c-8d68-0109c6150f4f.xml, windot11/DOT11_AVAILABLE_CHANNEL_LIST, _DOT11_AVAILABLE_CHANNEL_LIST, *PDOT11_AVAILABLE_CHANNEL_LIST, DOT11_AVAILABLE_CHANNEL_LIST structure [Network Drivers Starting with Windows Vista], netvista.dot11_available_channel_list
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
-	DOT11_AVAILABLE_CHANNEL_LIST
product: Windows
targetos: Windows
req.typenames: "*PDOT11_AVAILABLE_CHANNEL_LIST, DOT11_AVAILABLE_CHANNEL_LIST"
req.product: Windows 10 or later.
---

# _DOT11_AVAILABLE_CHANNEL_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AVAILABLE_CHANNEL_LIST structure specifies the available operating frequency channel list
  of the 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/dsss--hrdsss--and-erp-phy-configuration">DSSS, HRDSSS, and ERP PHY
  configurations</a> that the NIC can operate with.


## -syntax


````
typedef struct _DOT11_AVAILABLE_CHANNEL_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              uChannelNumber[1];
} DOT11_AVAILABLE_CHANNEL_LIST, *PDOT11_AVAILABLE_CHANNEL_LIST;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_AVAILABLE_CHANNEL_LIST structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_AVAILABLE_CHANNEL_LIST_REVISION_1.



#### Size

This member must be set to 
       <b>sizeof</b>(DOT11_AVAILABLE_CHANNEL_LIST).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfEntries

The number of entries in the 
     <b>uChannelNumber</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>uChannelNumber</b> array can contain.


### -field uChannelNumber

An array that specifies the list of available operating frequency channels of the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/dsss--hrdsss--and-erp-phy-configuration">DSSS, HRDSSS, and ERP PHY
     configurations</a> that the NIC can operate with.


## -remarks



This structure is used with 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-available-channel-list">
    OID_DOT11_AVAILABLE_CHANNEL_LIST</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-available-channel-list">
   OID_DOT11_AVAILABLE_CHANNEL_LIST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_AVAILABLE_CHANNEL_LIST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

