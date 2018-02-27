---
UID: NS:windot11.DOT11_DISASSOCIATION_PARAMETERS
title: DOT11_DISASSOCIATION_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_disassociation_parameters.htm
old-project: netvista
ms.assetid: bf5f520e-4bbc-4b9f-9e6c-b430cb9e3b28
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_DISASSOCIATION_PARAMETERS, DOT11_DISASSOCIATION_PARAMETERS, DOT11_DISASSOCIATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_289b81c2-13d2-484b-9306-6ca3dc961675.xml, PDOT11_DISASSOCIATION_PARAMETERS, PDOT11_DISASSOCIATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_disassociation_parameters, windot11/DOT11_DISASSOCIATION_PARAMETERS, windot11/PDOT11_DISASSOCIATION_PARAMETERS"
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
-	DOT11_DISASSOCIATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_DISASSOCIATION_PARAMETERS, *PDOT11_DISASSOCIATION_PARAMETERS
req.product: Windows 10 or later.
---

# DOT11_DISASSOCIATION_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DISASSOCIATION_PARAMETERS structure specifies the results of the disassociation operation
  performed by the 802.11 station with either an access point (AP) or peer station. The Native 802.11
  miniport driver includes a DOT11_ASSOCIATION_DISASSOCIATION_PARAMETERS structure when the driver makes an 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
  NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication.


## -syntax


````
typedef struct DOT11_DISASSOCIATION_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  MacAddr;
  DOT11_ASSOC_STATUS uReason;
  ULONG              uIHVDataOffset;
  ULONG              uIHVDataSize;
} DOT11_DISASSOCIATION_PARAMETERS, *PDOT11_DISASSOCIATION_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_DISASSOCIATION_PARAMETERS structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_DISASSOCIATION_PARAMETERS_REVISION_1.



#### Size

This member must be set to 
       sizeof(DOT11_DISASSOCIATION_PARAMETERS).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field MacAddr

The media access control (MAC) address of the AP or peer station that the 802.11 station has
     disassociated from.
     

If the miniport driver sets 
     <b>MacAddr</b> to the wildcard value of 0xFFFFFFFFFFFF, the 802.11 station has disassociated from the AP
     or all peer stations.


### -field uReason

The reason for the disassociation formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a> value.


### -field uIHVDataOffset

The offset of a block of data in a proprietary format that is defined by the IHV. The IHV can use
      this data block for any purposes that are related to the 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
      NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication.

This offset is relative to the start of the buffer, which contains the
      DOT11_DISASSOCIATION_PARAMETERS structure.

If the miniport driver is not returning IHV data in the 
      NDIS_STATUS_DOT11_DISASSOCIATION indication, it must set uIHVDataOffset to
      zero.


### -field uIHVDataSize

The length of the block of data that is used by the IHV for the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
     NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication. If the miniport driver is not returning IHV
     data in this indication, it must set 
     <b>uIHVDataSize</b> to zero.


## -remarks



For more information about the disassociation operation, see 
    <a href="https://msdn.microsoft.com/3589a694-a69a-481f-8479-ea918287736d">Disassociation Operations</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
   NDIS_STATUS_DOT11_DISASSOCIATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_DISASSOCIATION_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

