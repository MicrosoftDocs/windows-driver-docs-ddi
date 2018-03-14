---
UID: NS:windot11._DOT11_STOP_AP_PARAMETERS
title: "_DOT11_STOP_AP_PARAMETERS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_stop_ap_parameters.htm
old-project: netvista
ms.assetid: a9dfb490-425a-4011-a008-ab1597f53b85
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_STOP_AP_PARAMETERS, DOT11_STOP_AP_PARAMETERS, DOT11_STOP_AP_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_1c8e69b9-852b-4ad6-87a4-ae13b37f7523.xml, PDOT11_STOP_AP_PARAMETERS, PDOT11_STOP_AP_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_STOP_AP_PARAMETERS, netvista.dot11_stop_ap_parameters, windot11/DOT11_STOP_AP_PARAMETERS, windot11/PDOT11_STOP_AP_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	windot11.h
api_name:
-	DOT11_STOP_AP_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_STOP_AP_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_STOP_AP_PARAMETERS structure specifies the reason why the NIC has stopped an 802.11 access
  point (AP).


## -syntax


````
typedef struct _DOT11_STOP_AP_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulReason;
} DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_STOP_AP_PARAMETERS structure. This member is formatted
     as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_STOP_AP_PARAMETERS_REVISION_1.



#### Size

This member must be set to 
       sizeof(DOT11_STOP_AP_PARAMETERS).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field ulReason

The reason why the NIC stopped the AP. An IHV can supply the following range of values:
     





#### DOT11_STOP_AP_REASON_AP_ACTIVE

The miniport driver determined that an AP is already active on another 802.11 MAC entity for
       this physical wireless LAN adapter.



#### DOT11_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE

The miniport driver determined that no valid operating frequency is available.



#### DOT11_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE

The miniport driver determined that no good operating channel is available.



#### DOT11_STOP_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.



#### DOT11_STOP_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

If the value of 
     <b>ulReason</b> is in the range of DOT11_STOP_AP_REASON_IHV_START and DOT11_STOP_AP_REASON_IHV_END,
     inclusive, the operating system takes no action.


## -remarks



The Native 802.11 miniport driver includes a DOT11_STOP_AP_PARAMETERS structure when the driver makes
    an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567366">NDIS_STATUS_DOT11_STOP_AP</a> status
    indication.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567366">NDIS_STATUS_DOT11_STOP_AP</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


