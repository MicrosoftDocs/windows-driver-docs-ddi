---
UID: NE:ehstorioctl._PDO_TYPE
title: _PDO_TYPE (ehstorioctl.h)
description: This enumeration describes the types of Physical Device Objects (PDOs).
old-location: storage\pdo_type.htm
tech.root: storage
ms.assetid: 9695d55c-a214-4bba-aba9-38dfa7f54ec9
ms.date: 03/29/2018
keywords: ["PDO_TYPE enumeration"]
ms.keywords: PDO_TYPE, PDO_TYPE enumeration [Storage Devices], PDO_TYPE_CONTROL, PDO_TYPE_DISK, PDO_TYPE_SILO, PDO_TYPE_THIS, PDO_TYPE_UNDEFINED, _PDO_TYPE, ehstorioctl/PDO_TYPE, ehstorioctl/PDO_TYPE_CONTROL, ehstorioctl/PDO_TYPE_DISK, ehstorioctl/PDO_TYPE_SILO, ehstorioctl/PDO_TYPE_THIS, ehstorioctl/PDO_TYPE_UNDEFINED, storage.pdo_type, structs-silo_9ef418bc-5275-4fcf-a49b-804ace353da8.xml
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
req.typenames: PDO_TYPE
f1_keywords:
 - _PDO_TYPE
 - ehstorioctl/_PDO_TYPE
 - PDO_TYPE
 - ehstorioctl/PDO_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - PDO_TYPE
---

# _PDO_TYPE enumeration


## -description

This enumeration describes the types of Physical Device Objects (PDOs).

## -enum-fields

### -field PDO_TYPE_UNDEFINED

Types either enumerated or provided as filter parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>

### -field PDO_TYPE_DISK

This value indicates the PDO is for a logical disk device.

### -field PDO_TYPE_CONTROL

This value indicates the PDO is for a logical control device.

### -field PDO_TYPE_SILO

This value indicates the PDO is for a logical silo device.

### -field PDO_TYPE_THIS

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>

