---
UID: NS:windot11._DOT11_STATUS_INDICATION
title: _DOT11_STATUS_INDICATION (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_status_indication.htm
tech.root: netvista
ms.assetid: 77b2eae8-1fa5-4f87-97e4-713bfca627b2
ms.date: 02/16/2018
keywords: ["DOT11_STATUS_INDICATION structure"]
ms.keywords: "*PDOT11_STATUS_INDICATION, DOT11_STATUS_INDICATION, DOT11_STATUS_INDICATION structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_4bd90807-e039-426f-a5d9-daa7bca20bad.xml, PDOT11_STATUS_INDICATION, PDOT11_STATUS_INDICATION structure pointer [Network Drivers Starting with Windows Vista], _DOT11_STATUS_INDICATION, netvista.dot11_status_indication, windot11/DOT11_STATUS_INDICATION, windot11/PDOT11_STATUS_INDICATION"
f1_keywords:
 - "windot11/DOT11_STATUS_INDICATION"
 - "DOT11_STATUS_INDICATION"
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
- DOT11_STATUS_INDICATION
targetos: Windows
req.typenames: DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION
product:
- Windows 10 or later.
---

# _DOT11_STATUS_INDICATION structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_STATUS_INDICATION structure returns the completion results of an operation that is
  performed by a set request of a Native 802.11 OID.


## -syntax


```cpp
typedef struct _DOT11_STATUS_INDICATION {
  ULONG       uStatusType;
  NDIS_STATUS ndisStatus;
} DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION;
```


## -struct-fields




### -field uStatusType

The type of status indication that is made by the miniport driver.


For more information about the value that is used for the
     <b>uStatusType</b> member, see the topic for the OID that requires a completion indication that uses the
     DOT11_STATUS_INDICATION structure.


### -field ndisStatus

An NDIS_STATUS value that indicates the result of the operation.


If the operation completed without a failure, the miniport driver must set the
     <b>ndisStatus</b> member to NDIS_STATUS_SUCCESS. Otherwise, the driver must set
     <b>ndisStatus</b> to the appropriate NDIS_STATUS_xxx value for the failure.


## -remarks



For the Windows Vista operating system, only
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a> requires the
    use of the DOT11_STATUS_INDICATION structure for completion indications.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>



 

 


