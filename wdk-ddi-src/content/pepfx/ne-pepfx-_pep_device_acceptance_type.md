---
UID: NE:pepfx._PEP_DEVICE_ACCEPTANCE_TYPE
title: _PEP_DEVICE_ACCEPTANCE_TYPE (pepfx.h)
description: The PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device.
old-location: kernel\pep_device_acceptance_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_DEVICE_ACCEPTANCE_TYPE enumeration"]
ms.keywords: "*PPEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE enumeration [Kernel-Mode Driver Architecture], PepDeviceAccepted, PepDeviceAcceptedMax, PepDeviceAcceptedReserved, PepDeviceNotAccepted, _PEP_DEVICE_ACCEPTANCE_TYPE, kernel.pep_device_acceptance_type, pepfx/PEP_DEVICE_ACCEPTANCE_TYPE, pepfx/PepDeviceAccepted, pepfx/PepDeviceAcceptedMax, pepfx/PepDeviceAcceptedReserved, pepfx/PepDeviceNotAccepted"
req.header: pepfx.h
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
 - pepfx/_PEP_DEVICE_ACCEPTANCE_TYPE
 - PPEP_DEVICE_ACCEPTANCE_TYPE
 - pepfx/PPEP_DEVICE_ACCEPTANCE_TYPE
 - PEP_DEVICE_ACCEPTANCE_TYPE
 - pepfx/PEP_DEVICE_ACCEPTANCE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_DEVICE_ACCEPTANCE_TYPE
---

# _PEP_DEVICE_ACCEPTANCE_TYPE enumeration (pepfx.h)


## -description

The <b>PEP_DEVICE_ACCEPTANCE_TYPE</b> enumeration indicates whether a PEP accepts ownership of a device.

## -enum-fields

### -field PepDeviceNotAccepted

The PEP does not claim ownership of this device.

### -field PepDeviceAccepted

The PEP claims ownership of this device.

### -field PepDeviceAceptedMax

#### - PepDeviceAcceptedMax

Reserved for use by operating system.


#### - PepDeviceAcceptedReserved

The PEP claims ownership of the device on behalf of the default PEP. The default PEP is implemented by the Windows kernel to manage devices for which hardware-specific PEPs are not available.

## -remarks

This enumeration is used by <b>DeviceAccepted</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_device_v2">PEP_REGISTER_DEVICE_V2</a> structure to indicate whether a PEP accepts ownership of a device.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_device_v2">PEP_REGISTER_DEVICE_V2</a>
