---
UID: NS:kdnetpf._NDIS_KDNET_BDF
tech.root: debugger
title: NDIS_KDNET_BDF (kdnetpf.h)
ms.date: 08/18/2023
targetos: Windows
description: "KDNETPF transport support API - The NDIS_KDNET_BDF structure describes the PCI location of the port to query." 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: kdnetpf.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_KDNET_BDF, *PNDIS_KDNET_PCI_BDF
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - kdnetpf.h
api_name:
 - _NDIS_KDNET_BDF
 - PNDIS_KDNET_PCI_BDF
 - NDIS_KDNET_BDF
f1_keywords:
 - _NDIS_KDNET_BDF
 - kdnetpf/_NDIS_KDNET_BDF
 - PNDIS_KDNET_PCI_BDF
 - kdnetpf/PNDIS_KDNET_PCI_BDF
 - NDIS_KDNET_BDF
 - kdnetpf/NDIS_KDNET_BDF
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_BDF
---

## -description

The **NDIS_KDNET_BDF** structure describes the PCI location of the port to query.

## -struct-fields

### -field SegmentNumber

The PCI SegmentNumber.

### -field BusNumber

The PCI BusNumber.

### -field DeviceNumber

The PCI DeviceNumber.

### -field FunctionNumber

The PCI Function Number.

### -field Reserved

This field is reserved. Set to TBD.

## -remarks

## -see-also

[kdnetpf.h](index.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
