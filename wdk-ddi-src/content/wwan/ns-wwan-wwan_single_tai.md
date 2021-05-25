---
UID: NS:wwan._WWAN_SINGLE_TAI
tech.root: 
title: WWAN_SINGLE_TAI
description: The WWAN_SINGLE_TAI structure represents a single Tracking Area Identity (TAI).
ms.date: 
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_SINGLE_TAI, *PWWAN_SINGLE_TAI
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SINGLE_TAI
 - PWWAN_SINGLE_TAI
 - WWAN_SINGLE_TAI
f1_keywords:
 - _WWAN_SINGLE_TAI
 - wwan/_WWAN_SINGLE_TAI
 - PWWAN_SINGLE_TAI
 - wwan/PWWAN_SINGLE_TAI
 - WWAN_SINGLE_TAI
 - wwan/WWAN_SINGLE_TAI
dev_langs:
 - c++
---

## -description

The **WWAN_SINGLE_TAI** structure represents a single Tracking Area Identity (TAI). The TAI contains the Mobile Country Code (MCC), Mobile Network Code (MNC) and Tracking Area Code (TAC)).

## -struct-fields

### -field Mcc

Mobile Country Code of 3 decimal digits. The least significant 12 bits contains BCD-encoded 3 decimal digits sequentially for the MCC, with the last digit of the MCC in the least significant 4 bits. The unused bits in the UINT16 integer must be zeros.

### -field Mnc

Mobile Network Code of either 3 or 2 decimal digits. The most significant bit indicates whether the MNC has 2 decimal digits or 3 decimal digits. If this bit has 1, the MNC has 2 decimal digits and the least significant 8 bits contains them in BCD-encoded form sequentially, with the last digit of the MNC in the least significant 4 bits. If the most significant bit has 0, the MNC has 3 decimal digits and the least significant 12 bits contains them in BCD-encoded form sequentially, with the last digit of the MNC in the least significant 4 bits. The unused bits in the UINT16 integer must be zeros.

### -field Tac

Tracking Area Code. If TAC is unknown or invalid, entire TAI is unknown and the MCC component of the field above should be set as mentioned above.

## -remarks

## -see-also

[MB Packet Service Operations](/windows-hardware/drivers/network/mb-packet-service-attach-operations)

[OID_WWAN_PACKET_SERVICE](/windows-hardware/drivers/network/oid-wwan-packet-service)

[NDIS_STATUS_WWAN_PACKET_SERVICE](/windows-hardware/drivers/network/ndis-status-wwan-packet-service)
