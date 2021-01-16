---
UID: NE:fwpsk.FWPS_VSWITCH_EVENT_TYPE_
title: FWPS_VSWITCH_EVENT_TYPE_ (fwpsk.h)
description: The FWPS_VSWITCH_EVENT_TYPE enumeration type specifies the type of a virtual switch event notification.
old-location: netvista\fwps_vswitch_event_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_VSWITCH_EVENT_TYPE_ enumeration"]
ms.keywords: FWPS_VSWITCH_EVENT_INTERFACE_CREATE, FWPS_VSWITCH_EVENT_INTERFACE_DELETE, FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT, FWPS_VSWITCH_EVENT_POLICY_ADD, FWPS_VSWITCH_EVENT_POLICY_DELETE, FWPS_VSWITCH_EVENT_POLICY_UPDATE, FWPS_VSWITCH_EVENT_PORT_CREATE, FWPS_VSWITCH_EVENT_PORT_DELETE, FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE, FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE, FWPS_VSWITCH_EVENT_TYPE, FWPS_VSWITCH_EVENT_TYPE enumeration [Network Drivers Starting with Windows Vista], FWPS_VSWITCH_EVENT_TYPE_, FWPS_VSWITCH_EVENT_VSWITCH_CREATE, FWPS_VSWITCH_EVENT_VSWITCH_DELETE, FWPS_VSWITCH_EVENT_VSWITCH_NONE, fwpsk/FWPS_VSWITCH_EVENT_INTERFACE_CREATE, fwpsk/FWPS_VSWITCH_EVENT_INTERFACE_DELETE, fwpsk/FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT, fwpsk/FWPS_VSWITCH_EVENT_POLICY_ADD, fwpsk/FWPS_VSWITCH_EVENT_POLICY_DELETE, fwpsk/FWPS_VSWITCH_EVENT_POLICY_UPDATE, fwpsk/FWPS_VSWITCH_EVENT_PORT_CREATE, fwpsk/FWPS_VSWITCH_EVENT_PORT_DELETE, fwpsk/FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE, fwpsk/FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE, fwpsk/FWPS_VSWITCH_EVENT_TYPE, fwpsk/FWPS_VSWITCH_EVENT_VSWITCH_CREATE, fwpsk/FWPS_VSWITCH_EVENT_VSWITCH_DELETE, fwpsk/FWPS_VSWITCH_EVENT_VSWITCH_NONE, netvista.fwps_vswitch_event_type
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: FWPS_VSWITCH_EVENT_TYPE
f1_keywords:
 - FWPS_VSWITCH_EVENT_TYPE_
 - fwpsk/FWPS_VSWITCH_EVENT_TYPE_
 - FWPS_VSWITCH_EVENT_TYPE
 - fwpsk/FWPS_VSWITCH_EVENT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_VSWITCH_EVENT_TYPE_
 - FWPS_VSWITCH_EVENT_TYPE
---

# FWPS_VSWITCH_EVENT_TYPE_ enumeration


## -description

The FWPS_VSWITCH_EVENT_TYPE enumeration type specifies the type of a virtual switch event notification.

## -enum-fields

### -field FWPS_VSWITCH_EVENT_VSWITCH_NONE

Indicates no specific virtual switch event.

### -field FWPS_VSWITCH_EVENT_VSWITCH_CREATE

Indicates that the virtual switch instance was created.

### -field FWPS_VSWITCH_EVENT_VSWITCH_DELETE

Indicates that the virtual switch instance was deleted.

### -field FWPS_VSWITCH_EVENT_PORT_CREATE

Indicates that the virtual switch port was created.

### -field FWPS_VSWITCH_EVENT_PORT_DELETE

Indicates that the virtual switch port was deleted.

### -field FWPS_VSWITCH_EVENT_INTERFACE_CREATE

Indicates that the virtual switch interface was created.

### -field FWPS_VSWITCH_EVENT_INTERFACE_DELETE

Indicates that the virtual switch interface was deleted.

### -field FWPS_VSWITCH_EVENT_INTERFACE_CONNECT

Indicates that the virtual switch interface was connected.

### -field FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT

Indicates that the virtual switch interface was disconnected.

### -field FWPS_VSWITCH_EVENT_POLICY_ADD

Indicates the addition of a policy for a virtual switch port.

### -field FWPS_VSWITCH_EVENT_POLICY_UPDATE

Indicates a policy update to a virtual switch port.

### -field FWPS_VSWITCH_EVENT_POLICY_DELETE

Indicates the deletion of a policy for a virtual switch port.

### -field FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE

Indicates a virtual switch run-time state save event.

### -field FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE

Indicates a virtual switch run-time state restore event.

## -remarks

The 
    FWPS_VSWITCH_EVENT_TYPE  enumeration defines the values for the <i>eventType</i> parameter of the  virtual switch notification functions that are included in the <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_vswitch_event_dispatch_table0_">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_vswitch_event_dispatch_table0_">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a>

