---
UID: NS:windot11._DOT11_CAN_SUSTAIN_AP_PARAMETERS
title: _DOT11_CAN_SUSTAIN_AP_PARAMETERS
author: windows-driver-content
description: The DOT11_CAN_SUSTAIN_AP_PARAMETERS structure specifies the reason why the NIC can sustain an access point (AP).
old-location: netvista\dot11_can_sustain_ap_parameters.htm
old-project: netvista
ms.assetid: 8d7995f3-6cc1-4f3c-a016-b31dc69ddd7f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_CAN_SUSTAIN_AP_PARAMETERS, windot11/PDOT11_CAN_SUSTAIN_AP_PARAMETERS, PDOT11_CAN_SUSTAIN_AP_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_can_sustain_ap_parameters, _DOT11_CAN_SUSTAIN_AP_PARAMETERS, PDOT11_CAN_SUSTAIN_AP_PARAMETERS, Native_802.11_data_types_4f647d9c-29f9-4b57-9906-e66d1a76272a.xml, windot11/DOT11_CAN_SUSTAIN_AP_PARAMETERS, DOT11_CAN_SUSTAIN_AP_PARAMETERS structure [Network Drivers Starting with Windows Vista], *PDOT11_CAN_SUSTAIN_AP_PARAMETERS
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
-	DOT11_CAN_SUSTAIN_AP_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_CAN_SUSTAIN_AP_PARAMETERS, *PDOT11_CAN_SUSTAIN_AP_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_CAN_SUSTAIN_AP_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CAN_SUSTAIN_AP_PARAMETERS structure specifies the reason why the NIC can sustain an access
   point (AP).


## -syntax


````
typedef struct _DOT11_CAN_SUSTAIN_AP_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulReason;
} DOT11_CAN_SUSTAIN_AP_PARAMETERS, *PDOT11_CAN_SUSTAIN_AP_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_CAN_SUSTAIN_AP_PARAMETERS structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field ulReason

A ULONG value that specifies the reason why the NIC can sustain the AP. An IHV can supply the
     following range of values:
     



If the value of 
     <b>ulReason</b> is in the range of DOT11_CAN_SUSTAIN_AP_REASON_IHV_START and
     DOT11_STOP_AP_REASON_IHV_END, inclusive, the operating system takes no action.


##### - Header.Revision

This member must be set to DOT11_CAN_SUSTAIN_AP_PARAMETERS_REVISION_1.


##### - Header.Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


##### - Header.Size

This member must be set to 
       <b>sizeof</b>(DOT11_CAN_SUSTAIN_AP_PARAMETERS).


##### - ulReason.DOT11_CAN_SUSTAIN_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.


##### - ulReason.DOT11_CAN_SUSTAIN_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.


## -remarks


The Native 802.11 miniport driver includes a DOT11_CAN_SUSTAIN_AP_PARAMETERS structure when the driver
    makes an 
    <mshelp:link keywords="netvista.ndis_status_dot11_can_sustain_ap" tabindex="0">
    NDIS_STATUS_DOT11_CAN_SUSTAIN_AP</mshelp:link> status indication.



## -see-also

<mshelp:link keywords="netvista.ndis_status_dot11_can_sustain_ap" tabindex="0">
   NDIS_STATUS_DOT11_CAN_SUSTAIN_AP</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CAN_SUSTAIN_AP_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

