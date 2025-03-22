---
UID: NE:dot11wificxtypes._WDI_ACTION_FRAME_CATEGORY
tech.root: netvista
title: WDI_ACTION_FRAME_CATEGORY
ms.date: 03/04/2024
targetos: Windows
description: The WDI_ACTION_FRAME_CATEGORY enumeration defines action frame categories.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_ACTION_FRAME_CATEGORY
 - WDI_ACTION_FRAME_CATEGORY
f1_keywords:
 - _WDI_ACTION_FRAME_CATEGORY
 - dot11wificxtypes/_WDI_ACTION_FRAME_CATEGORY
 - WDI_ACTION_FRAME_CATEGORY
 - dot11wificxtypes/WDI_ACTION_FRAME_CATEGORY
dev_langs:
 - c++
---

# WDI_ACTION_FRAME_CATEGORY enumeration (dot11wificxtypes.h)

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_ACTION_FRAME_CATEGORY** enumeration defines action frame categories.

## -enum-fields

### -field WDI_ACTION_FRAME_CATEGORY_SPECTRUM_MANAGEMENT:0

Spectrum Management Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_QOS:1

QoS Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_RESERVED:2

Reserved.

### -field WDI_ACTION_FRAME_CATEGORY_BLOCK_ACK:3

Block Acknowledgement Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_PUBLIC:4

Public Action frame category.  It is used in:

* Inter-BSS and AP to unassociated-STA communications
* Intra-BSS communication<
* GAS frames

### -field WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT:5

Radio Measurement Report frame category. It is transmitted by a STA requesting another STA to make one or more measurements on one or more channels.

### -field WDI_ACTION_FRAME_CATEGORY_FAST_BSS_TRANSITION:6    

Fast BSS Transition Action frame category.  It is used by a currently-associated AP to enable fast BSS transitions over the DS.  Over the DS transitions are not supported in Windows 10.

### -field WDI_ACTION_FRAME_CATEGORY_HT:7

HT Action frame category. 

### -field WDI_ACTION_FRAME_CATEGORY_SA_QUERY:8

SA Query Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_PROTECTED_DUAL_OF_PUBLIC_ACTION:9

Protected Dual of Public Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_WNM:10

Wireless Network Management Action frame category.  In Windows 10, it is only used for handling BSS Transition Management requests/responses.

### -field WDI_ACTION_FRAME_CATEGORY_UNPROTECTED_WNM:11

Unprotected Wireless Network Management Action frame category.

### -field WDI_ACTION_FRAME_CATEGORY_ROBUST_AV_STREAMING:19

Robust AV Streaming Action frame category.

## -remarks

## -see-also



