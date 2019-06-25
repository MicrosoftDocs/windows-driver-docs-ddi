---
UID: NS:windot11._DOT11_CAN_SUSTAIN_AP_PARAMETERS
title: _DOT11_CAN_SUSTAIN_AP_PARAMETERS (windot11.h)
description: The DOT11_CAN_SUSTAIN_AP_PARAMETERS structure specifies the reason why the NIC can sustain an access point (AP).
old-location: netvista\dot11_can_sustain_ap_parameters.htm
tech.root: netvista
ms.assetid: 8d7995f3-6cc1-4f3c-a016-b31dc69ddd7f
ms.date: 02/16/2018
ms.keywords: "*PDOT11_CAN_SUSTAIN_AP_PARAMETERS, DOT11_CAN_SUSTAIN_AP_PARAMETERS, DOT11_CAN_SUSTAIN_AP_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_4f647d9c-29f9-4b57-9906-e66d1a76272a.xml, PDOT11_CAN_SUSTAIN_AP_PARAMETERS, PDOT11_CAN_SUSTAIN_AP_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_CAN_SUSTAIN_AP_PARAMETERS, netvista.dot11_can_sustain_ap_parameters, windot11/DOT11_CAN_SUSTAIN_AP_PARAMETERS, windot11/PDOT11_CAN_SUSTAIN_AP_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_CAN_SUSTAIN_AP_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_CAN_SUSTAIN_AP_PARAMETERS, *PDOT11_CAN_SUSTAIN_AP_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_CAN_SUSTAIN_AP_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CAN_SUSTAIN_AP_PARAMETERS structure specifies the reason why the NIC can sustain an access
   point (AP).


## -syntax


```cpp
typedef struct _DOT11_CAN_SUSTAIN_AP_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulReason;
} DOT11_CAN_SUSTAIN_AP_PARAMETERS, *PDOT11_CAN_SUSTAIN_AP_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_CAN_SUSTAIN_AP_PARAMETERS structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_CAN_SUSTAIN_AP_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_CAN_SUSTAIN_AP_PARAMETERS).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field ulReason

A ULONG value that specifies the reason why the NIC can sustain the AP. An IHV can supply the
     following range of values:






#### DOT11_CAN_SUSTAIN_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.



#### DOT11_CAN_SUSTAIN_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

If the value of
     <b>ulReason</b> is in the range of DOT11_CAN_SUSTAIN_AP_REASON_IHV_START and
     DOT11_STOP_AP_REASON_IHV_END, inclusive, the operating system takes no action.


## -remarks



The Native 802.11 miniport driver includes a DOT11_CAN_SUSTAIN_AP_PARAMETERS structure when the driver
    makes an
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-can-sustain-ap">
    NDIS_STATUS_DOT11_CAN_SUSTAIN_AP</a> status indication.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-can-sustain-ap">
   NDIS_STATUS_DOT11_CAN_SUSTAIN_AP</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


