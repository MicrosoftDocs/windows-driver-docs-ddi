---
UID: NS:windot11._DOT11_ADDITIONAL_IE
title: "_DOT11_ADDITIONAL_IE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_additional_ie.htm
old-project: netvista
ms.assetid: db034863-f5fa-42bb-81c8-23d4784e0abe
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Native_802.11_data_types_306f816b-e8fa-4f61-be10-5fd4d793f5a5.xml, windot11/PDOT11_ADDITIONAL_IE, PDOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE structure [Network Drivers Starting with Windows Vista], DOT11_ADDITIONAL_IE, _DOT11_ADDITIONAL_IE, windot11/DOT11_ADDITIONAL_IE, PDOT11_ADDITIONAL_IE structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_additional_ie
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
-	DOT11_ADDITIONAL_IE
product: Windows
targetos: Windows
req.typenames: DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE
req.product: Windows 10 or later.
---

# _DOT11_ADDITIONAL_IE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ADDITIONAL_IE structure specifies characteristics of additional information elements (IEs)
  for a BSS 802.11 Beacon or Probe Response frame.


## -syntax


````
typedef struct _DOT11_ADDITIONAL_IE {
  NDIS_OBJECT_HEADER Header;
  ULONG              uBeaconIEsOffset;
  ULONG              uBeaconIEsLength;
  ULONG              uResponseIEsOffset;
  ULONG              uResponseIEsLength;
} DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_ADDITIONAL_IE structure. This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ADDITIONAL_IE_REVISION_1.



#### Size

This member must be set to 
       <b>sizeof</b>(DOT11_ADDITIONAL_IE).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uBeaconIEsOffset

The offset of the additional IEs, in bytes, in the beacon frame sent by the NIC. This offset is
     relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The default value
     is 0.


### -field uBeaconIEsLength

The length of the additional IEs, in bytes, in the beacon frame sent by the NIC. The default value
     is 0.


### -field uResponseIEsOffset

The offset of the additional IEs, in bytes, in the probe response frame sent by the NIC. This
     offset is relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The
     default value is 0.


### -field uResponseIEsLength

The length of the additional IEs, in bytes, in the probe response frame sent by the NIC. The
     default value is 0.


## -remarks



This structure is used with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569103">OID_DOT11_ADDITIONAL_IE</a>.

The miniport driver should reset the members of the DOT11_ADDITIONAL_IE structure to the default
    values when it receives an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a> request.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569103">OID_DOT11_ADDITIONAL_IE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ADDITIONAL_IE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

