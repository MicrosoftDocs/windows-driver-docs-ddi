---
UID: NE:portcls.PC_REBALANCE_TYPE
title: PC_REBALANCE_TYPE (portcls.h)
description: The PC_REBALANCE_TYPE enum describes the type of support for rebalancing.
old-location: audio\pc_rebalance_type.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PC_REBALANCE_TYPE enumeration"]
ms.keywords: PC_REBALANCE_TYPE, PC_REBALANCE_TYPE enumeration [Audio Devices], PcRebalanceNotSupported, PcRebalanceRemoveSubdevices, audio.pc_rebalance_type, portcls/PC_REBALANCE_TYPE, portcls/PcRebalanceNotSupported, portcls/PcRebalanceRemoveSubdevices
req.header: portcls.h
req.include-header: Portcls.h
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
req.typenames: PC_REBALANCE_TYPE
f1_keywords:
 - PC_REBALANCE_TYPE
 - portcls/PC_REBALANCE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - portcls.h
api_name:
 - PC_REBALANCE_TYPE
---

# PC_REBALANCE_TYPE enumeration


## -description

The <code>PC_REBALANCE_TYPE</code> enum describes the type of support for rebalancing.

## -enum-fields

### -field PcRebalanceNotSupported

Indicates that PcRebalance is not supported.

### -field PcRebalanceRemoveSubdevices

Indicates that PcRebalance is supported via unregistering and re-registering the audio subdevices.

## -remarks

 Rebalancing is used in certain PCI scenarios. For example when additional devices are added to the PCI chain and the use of memory resources needs to be rearranged and consolidated.

For more information,  see <a href="/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>.

Available in Windows 10, version 1511 and later versions of Windows.

