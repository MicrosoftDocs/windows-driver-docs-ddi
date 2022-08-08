---
UID: NE:pep_x._PEP_DEVICE_ACCEPTANCE_TYPE
title: _PEP_DEVICE_ACCEPTANCE_TYPE (pep_x.h)
description: Learn how the PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device.
old-location: kernel\pep_device_acceptance_type.htm
tech.root: kernel
ms.date: 08/05/2022
keywords: ["PEP_DEVICE_ACCEPTANCE_TYPE enumeration"]
ms.keywords: "*PPEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE enumeration [Kernel-Mode Driver Architecture], PepDeviceAccepted, PepDeviceAcceptedMax, PepDeviceAcceptedReserved, PepDeviceNotAccepted, _PEP_DEVICE_ACCEPTANCE_TYPE, kernel.pep_device_acceptance_type, pepfx/PEP_DEVICE_ACCEPTANCE_TYPE, pepfx/PepDeviceAccepted, pepfx/PepDeviceAcceptedMax, pepfx/PepDeviceAcceptedReserved, pepfx/PepDeviceNotAccepted"
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.typenames: PEP_DEVICE_ACCEPTANCE_TYPE, *PPEP_DEVICE_ACCEPTANCE_TYPE
f1_keywords:
 - _PEP_DEVICE_ACCEPTANCE_TYPE
 - pep_x/_PEP_DEVICE_ACCEPTANCE_TYPE
 - PPEP_DEVICE_ACCEPTANCE_TYPE
 - pep_x/PPEP_DEVICE_ACCEPTANCE_TYPE
 - PEP_DEVICE_ACCEPTANCE_TYPE
 - pep_x/PEP_DEVICE_ACCEPTANCE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_DEVICE_ACCEPTANCE_TYPE
 - PPEP_DEVICE_ACCEPTANCE_TYPE
 - PEP_DEVICE_ACCEPTANCE_TYPE
---

# _PEP_DEVICE_ACCEPTANCE_TYPE enumeration (pep_x.h)

## -description

The **PEP_DEVICE_ACCEPTANCE_TYPE** enumeration indicates whether a PEP accepts ownership of a device.

## -enum-fields

### -field PepDeviceNotAccepted

The PEP does not claim ownership of this device.

### -field PepDeviceAcceptedFull

The PEP claims full ownership of this device.

### -field PepDeviceAceptedMax

Reserved for use by operating system.

## -remarks

This enumeration is used by **DeviceAccepted** member of the [PEP_REGISTER_DEVICE_V2](../pepfx/ns-pepfx-_pep_register_device_v2.md) structure to indicate whether a PEP accepts ownership of a device.

## -see-also

[PEP_REGISTER_DEVICE_V2](../pepfx/ns-pepfx-_pep_register_device_v2.md)
