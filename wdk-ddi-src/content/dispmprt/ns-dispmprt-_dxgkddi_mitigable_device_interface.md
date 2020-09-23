---
UID: NS:dispmprt._DXGKDDI_MITIGABLE_DEVICE_INTERFACE
title: _DXGKDDI_MITIGABLE_DEVICE_INTERFACE
description: This device interface specifies the parts of the device base address registers that need to be intercepted and mitigated.
tech.root: display
ms.assetid: 77323c81-e0e9-47e0-9a99-b277fc678ee3
ms.date: 04/04/2019
keywords: ["DXGKDDI_MITIGABLE_DEVICE_INTERFACE structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKDDI_MITIGABLE_DEVICE_INTERFACE, DXGKDDI_MITIGABLE_DEVICE_INTERFACE, *PDXGKDDI_MITIGABLE_DEVICE_INTERFACE,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKDDI_MITIGABLE_DEVICE_INTERFACE, *PDXGKDDI_MITIGABLE_DEVICE_INTERFACE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKDDI_MITIGABLE_DEVICE_INTERFACE
 - dispmprt/_DXGKDDI_MITIGABLE_DEVICE_INTERFACE
 - PDXGKDDI_MITIGABLE_DEVICE_INTERFACE
 - dispmprt/PDXGKDDI_MITIGABLE_DEVICE_INTERFACE
 - DXGKDDI_MITIGABLE_DEVICE_INTERFACE
 - dispmprt/DXGKDDI_MITIGABLE_DEVICE_INTERFACE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKDDI_MITIGABLE_DEVICE_INTERFACE
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKDDI_MITIGABLE_DEVICE_INTERFACE structure


## -description

This device interface specifies the parts of the device base address registers that need to be intercepted and mitigated. 

These ranges could be sections of the hardware that are protected or could result in crashes or exploits from the guest virtual machine if they were exposed.  As part of a defense-in-depth approach, these sensitive hardware regions are exposed and protected not by the user mode device emulator, but instead by the more trusted kernel mode device driver.

## -struct-fields

### -field Size

Size.

### -field Version

Represents the DXGKDDI_MITIGABLE_DEVICE_INTERFACE_VERSION.

### -field Context

Device context.

### -field InterfaceReference

Reference.

### -field InterfaceDereference

Dereference.

### -field DxgkDdiQueryMitigatedRangeCount

Called to query the mitigated range count.

### -field DxgkDdiQueryMitigatedRanges

 
Called to query the mitigated ranges.

## -remarks

This interface is optional but must be implemented for any GPU where a virtual function has hardware resources, which are unsafe to directly expose to a VM. If a driver uses mitigation, it must also provide a user mode emulation DLL that implements the mitigation. 
The KMD could decide that the mitigated ranges need remapping and DxgkCbMitigatedRangeUpdate callback is provided to notify Dxgkrnl. Dxgkrnl will re-enumerate mitigated ranges asynchronously.

## -see-also

