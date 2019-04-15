---
UID: NS:windot11.DOT11_ROAMING_COMPLETION_PARAMETERS
title: DOT11_ROAMING_COMPLETION_PARAMETERS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_roaming_completion_parameters.htm
tech.root: netvista
ms.assetid: 535857c5-dd71-4575-8475-ff6c7c934dbe
ms.date: 02/16/2018
ms.keywords: "*PDOT11_ROAMING_COMPLETION_PARAMETERS, DOT11_ROAMING_COMPLETION_PARAMETERS, DOT11_ROAMING_COMPLETION_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_49eb3670-7bdc-41ad-b143-cb9d1be8c32f.xml, PDOT11_ROAMING_COMPLETION_PARAMETERS, PDOT11_ROAMING_COMPLETION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_roaming_completion_parameters, windot11/DOT11_ROAMING_COMPLETION_PARAMETERS, windot11/PDOT11_ROAMING_COMPLETION_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_ROAMING_COMPLETION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_ROAMING_COMPLETION_PARAMETERS, *PDOT11_ROAMING_COMPLETION_PARAMETERS
product:
- Windows 10 or later.
---

# DOT11_ROAMING_COMPLETION_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ROAMING_COMPLETION_PARAMETERS structure specifies the completion results of the roaming
  operation performed by the Native 802.11 miniport driver. The driver includes a
  DOT11_ROAMING_COMPLETION_PARAMETERS structure when the driver makes an
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-roaming-completion">
  NDIS_STATUS_DOT11_ROAMING_COMPLETION</a> status indication.


## -syntax


```cpp
typedef struct DOT11_ROAMING_COMPLETION_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_ASSOC_STATUS uStatus;
} DOT11_ROAMING_COMPLETION_PARAMETERS, *PDOT11_ROAMING_COMPLETION_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_ROAMING_COMPLETION_PARAMETERS structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <i>Header</i> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ROAMING_COMPLETION_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       <code>sizeof(DOT11_ROAMING_COMPLETION_PARAMETERS)</code>.

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The completion status of the roaming operation formatted as a
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a> value.


## -remarks



For more information about the roaming operation, see
    <a href="https://msdn.microsoft.com/b52e134e-4f26-4797-af57-dd7da177c193">Roaming Operations</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-roaming-completion">
   NDIS_STATUS_DOT11_ROAMING_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>



 

 


