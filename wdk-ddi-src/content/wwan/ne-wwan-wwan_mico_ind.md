---
UID: NE:wwan._WWAN_MICO_IND
tech.root: 
title: WWAN_MICO_IND
description: The WWAN_MICO_IND enumeration indicates the use of Mobile Initiated Connection (MICO) mode or the renegotiation of MICO mode.
ms.date: 
targetos: Windows
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MICO_IND
 - WWAN_MICO_IND
f1_keywords:
 - _WWAN_MICO_IND
 - wwan/_WWAN_MICO_IND
 - WWAN_MICO_IND
 - wwan/WWAN_MICO_IND
dev_langs:
 - c++
---

## -description

The **WWAN_MICO_IND** enumeration indicates the use of Mobile Initiated Connection (MICO) mode or the renegotiation of MICO mode. MICO is a mode of operation for 5G devices.

## -enum-fields

### -field WwanRaaiTypeRaNotAllocated

All public land mobile network (PLMN) registration area not allocated.

### -field WwanRaaiTypeRaAllocated

All PLMN registration area allocated.

### -field WwanRaaiTypeNotAvailable

Registration Area Allocation Indication (RAAI) not received from the network. Either the device did not send a MICO mode request, MICO mode is not supported by the network, or the device is not registered.

## -remarks

The RAAI values indicate the MICO mode negotiated with the network. If the device sends a MICO mode request and it is supported and accepted by the network, the network will include a MICO indication response when accepting the registration procedure.

## -see-also
