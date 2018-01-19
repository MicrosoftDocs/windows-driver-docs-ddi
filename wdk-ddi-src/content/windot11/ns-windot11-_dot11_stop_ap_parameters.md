---
UID: NS:windot11._DOT11_STOP_AP_PARAMETERS
title: _DOT11_STOP_AP_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_stop_ap_parameters.htm
old-project: netvista
ms.assetid: a9dfb490-425a-4011-a008-ab1597f53b85
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_STOP_AP_PARAMETERS, DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS
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
req.alt-api: DOT11_STOP_AP_PARAMETERS
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
req.typenames: DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_STOP_AP_PARAMETERS structure



## -description

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




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_STOP_AP_PARAMETERS_REVISION_1.


### -field Size

This member must be set to 
       sizeof(DOT11_STOP_AP_PARAMETERS).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field ulReason

The reason why the NIC stopped the AP. An IHV can supply the following range of values:
     




### -field DOT11_STOP_AP_REASON_AP_ACTIVE

The miniport driver determined that an AP is already active on another 802.11 MAC entity for
       this physical wireless LAN adapter.


### -field DOT11_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE

The miniport driver determined that no valid operating frequency is available.


### -field DOT11_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE

The miniport driver determined that no good operating channel is available.


### -field DOT11_STOP_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.


### -field DOT11_STOP_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

</dd>
</dl>
If the value of 
     <b>ulReason</b> is in the range of DOT11_STOP_AP_REASON_IHV_START and DOT11_STOP_AP_REASON_IHV_END,
     inclusive, the operating system takes no action.


## -remarks
The Native 802.11 miniport driver includes a DOT11_STOP_AP_PARAMETERS structure when the driver makes
    an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567366">NDIS_STATUS_DOT11_STOP_AP</a> status
    indication.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567366">NDIS_STATUS_DOT11_STOP_AP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_STOP_AP_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

