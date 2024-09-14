---
UID: NS:windot11._DOT11_STATUS_INDICATION
title: _DOT11_STATUS_INDICATION (windot11.h)
description: The DOT11_STATUS_INDICATION structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_status_indication.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_STATUS_INDICATION structure"]
ms.keywords: "*PDOT11_STATUS_INDICATION, DOT11_STATUS_INDICATION, DOT11_STATUS_INDICATION structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_4bd90807-e039-426f-a5d9-daa7bca20bad.xml, PDOT11_STATUS_INDICATION, PDOT11_STATUS_INDICATION structure pointer [Network Drivers Starting with Windows Vista], _DOT11_STATUS_INDICATION, netvista.dot11_status_indication, windot11/DOT11_STATUS_INDICATION, windot11/PDOT11_STATUS_INDICATION"
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
targetos: Windows
req.typenames: DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION
f1_keywords:
 - _DOT11_STATUS_INDICATION
 - windot11/_DOT11_STATUS_INDICATION
 - PDOT11_STATUS_INDICATION
 - windot11/PDOT11_STATUS_INDICATION
 - DOT11_STATUS_INDICATION
 - windot11/DOT11_STATUS_INDICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_STATUS_INDICATION
 - PDOT11_STATUS_INDICATION
 - DOT11_STATUS_INDICATION
---

# _DOT11_STATUS_INDICATION structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_STATUS_INDICATION structure returns the completion results of an operation that is
  performed by a set request of a Native 802.11 OID.

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

## -syntax

```cpp
typedef struct _DOT11_STATUS_INDICATION {
  ULONG       uStatusType;
  NDIS_STATUS ndisStatus;
} DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION;
```

## -remarks

For the Windows Vista operating system, only
    <a href="/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a> requires the
    use of the DOT11_STATUS_INDICATION structure for completion indications.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>

