---
UID: NE:pktmondefk._PKTMON_CAPTURE_TYPE
tech.root: netvista
title: PKTMON_CAPTURE_TYPE
ms.date: 11/11/2025
targetos: Windows
description: THe PKTMON_CAPTURE_TYPE enum specifies the type of packets to capture during packet monitoring.
ai-usage: ai-assisted
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: pktmondefk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmondefk.h
api_name:
 - _PKTMON_CAPTURE_TYPE
 - PKTMON_CAPTURE_TYPE
f1_keywords:
 - _PKTMON_CAPTURE_TYPE
 - pktmondefk/_PKTMON_CAPTURE_TYPE
 - PKTMON_CAPTURE_TYPE
 - pktmondefk/PKTMON_CAPTURE_TYPE
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_CAPTURE_TYPE
---

## -description

The **PKTMON_CAPTURE_TYPE** enum specifies the type of packets to capture during packet monitoring. This enumeration is used when starting packet monitoring to control whether to capture all packets, only successfully flowing packets, only dropped packets, or no packets at all.

The capture type is specified when starting packet monitoring and determines which packets are reported by the packet monitor. For a packet monitoring session, the capture type controls whether flow events and drop events are enabled for the monitored components.

## -enum-fields

### -field PktMonCapture_All

Capture all packets. Both flow packets and drop packets will be captured.

### -field PktMonCapture_Flow

Capture flow packets only. Only packets that are successfully flowing through the network stack will be captured.

### -field PktMonCapture_Drop

Capture drop packets only. Only packets that are dropped by the network stack will be captured.

### -field PktMonCapture_None

Capture no packets. Packet capturing is disabled.

## -remarks

## -see-also

- [PktMonClntNblLog](../pktmonclntk/nf-pktmonclntk-pktmonclntnbllog.md)
- [PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-PktMonClntNblDrop.md)
- [PktMonClntComponentRegister](../pktmonclntk/nf-pktmonclntk-PktMonClntComponentRegister.md)
