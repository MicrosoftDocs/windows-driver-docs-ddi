---
UID: NS:storport.PRI_FULL_STATUS_DESCRIPTOR_HEADER
tech.root: storage
title: PRI_FULL_STATUS_DESCRIPTOR_HEADER (storport.h)
ms.date: 03/22/2024
targetos: Windows
description: The PRI_FULL_STATUS_DESCRIPTOR_HEADER structure is the first member of a PRI_FULL_STATUS_DESCRIPTOR structure, which is used to populate a PRI_FULL_STATUS_LIST.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PRI_FULL_STATUS_DESCRIPTOR_HEADER, *PPRI_FULL_STATUS_DESCRIPTOR_HEADER
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PRI_FULL_STATUS_DESCRIPTOR_HEADER
 - PPRI_FULL_STATUS_DESCRIPTOR_HEADER
f1_keywords:
 - PRI_FULL_STATUS_DESCRIPTOR_HEADER
 - storport/PRI_FULL_STATUS_DESCRIPTOR_HEADER
 - PPRI_FULL_STATUS_DESCRIPTOR_HEADER
 - storport/PPRI_FULL_STATUS_DESCRIPTOR_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - PRI_FULL_STATUS_DESCRIPTOR_HEADER
---

## -description

The **PRI_FULL_STATUS_DESCRIPTOR_HEADER** structure is the first member of a **[PRI_FULL_STATUS_DESCRIPTOR](ns-storport-pri_full_status_descriptor.md)** structure, which is used to populate a **[PRI_FULL_STATUS_LIST](ns-storport-pri_full_status_list.md)**.

## -struct-fields

### -field ReservationKey[8]

The reservation key under which the persistent reservation is held.

### -field Reserved[4]

Reserved for internal use.

### -field ReservationHolder

A reservation holder set to one indicates that all initiator and target ports described by this full status descriptor are registered and are persistent reservation holders. A reservation holder set to zero indicates that all initiator and target ports described by this full status descriptor are registered but are not persistent reservation holders.

### -field AllTargetPorts

An *AllTargetPorts* value of zero indicates that this full status descriptor represents a single initiator port and target port pair. An *AllTargetPorts* value of one indicates:

- This full status descriptor represents all the initiator and target ports that are associated with both:
  - The initiator port (I) is specified by the *TransportID*
  - Every target port (T) is in the target device
- All the initiator and target ports are registered with the same reservation key
- All the initiator and target ports are either reservation holders or not reservation holders as indicated by the *ReservationHolder* field

### -field Reserved1

Reserved for internal use.

### -field Type

If *ReservationHolder* is set to one, the *Type* field is defined in the Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_READ_KEYS`. If *ReservationHolder* is set to zero, the contents of the *Type* field is not defined by this standard.

### -field Scope

If *ReservationHolder* is set to one, the *Scope* field is defined in the Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_READ_KEYS`. If *ReservationHolder* is set to zero, the contents of the *Scope* field is not defined by this standard.

### -field Reserved2[4]

Reserved for internal use.

### -field RelativeTargetPortIdentifier[2]

Identifies the target port relative to the initiator port.

### -field AdditionalDescriptorLength[4]

The *AdditionalDescriptorLength* field indicates the number of bytes that follow.

## -remarks

## -see-also

- **[PRI_FULL_STATUS_DESCRIPTOR](ns-storport-pri_full_status_descriptor.md)**
