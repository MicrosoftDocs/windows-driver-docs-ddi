---
UID: NS:scsi.__unnamed_struct_12
title: PRO_PARAMETER_LIST (scsi.h)
description: The PRO_PARAMETER_LIST structure is sent in a Persistent Reserve Out command to a device server.
old-location: storage\pro_parameter_list.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PRO_PARAMETER_LIST structure"]
ms.keywords: "*PPRO_PARAMETER_LIST, PPRO_PARAMETER_LIST, PPRO_PARAMETER_LIST structure pointer [Storage Devices], PRO_PARAMETER_LIST, PRO_PARAMETER_LIST structure [Storage Devices], storage.pro_parameter_list, storport/PPRO_PARAMETER_LIST, storport/PRO_PARAMETER_LIST, structs-general_7481edb0-cc60-44b9-abcc-80bf0f79fbae.xml"
req.header: scsi.h
req.include-header: Ntddstor.h, Minitape.h, Scsi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: PRO_PARAMETER_LIST, *PPRO_PARAMETER_LIST
f1_keywords:
 - PPRO_PARAMETER_LIST
 - scsi/PPRO_PARAMETER_LIST
 - PRO_PARAMETER_LIST
 - scsi/PRO_PARAMETER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PPRO_PARAMETER_LIST
 - PRO_PARAMETER_LIST
---

# PRO_PARAMETER_LIST structure (scsi.h)


## -description

The PRO_PARAMETER_LIST structure is sent in a Persistent Reserve Out command to a device server.

## -struct-fields

### -field ReservationKey

The ReservationKey field contains an 8-byte value that is provided by the application client to the device server. This value identifies the initiator that is the source of the Persistent Reserve Out command.

### -field ServiceActionReservationKey

The ServiceActionReservationKey field contains information that is needed for the following four service actions:

<ul>
<li>
REGISTER

</li>
<li>
REGISTER AND IGNORE EXISTING KEY

</li>
<li>
PREEMPT

</li>
<li>
PREEMPT AND ABORT

</li>
</ul>

### -field ScopeSpecificAddress

The ScopeSpecificAddress field contains the element address that has zeros placed in the most significant bits to fit the field. This is true if the scope of a reservation is set to ELEMENT_SCOPE. Otherwise, this field is set to all zeros.

### -field ActivatePersistThroughPowerLoss

The ActivatePersistThroughPowerLoss (APTPL) bit is valid only for the following service actions:

<ul>
<li>
REGISTER

</li>
<li>
REGISTER AND IGNORE EXISTING KEY

</li>
</ul>

### -field Reserved1

Reserved. Must be zero.

### -field Reserved2

Reserved. Must be zero.

### -field Obsolete

Reserved. Must be zero.

## -remarks

The <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_out">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a> request is used to control information about persistent reservations and reservation keys that are active within a device server.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_out">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a>

