---
UID: NS:dot11wdi._WDI_TX_COMPLETE_DATA
title: _WDI_TX_COMPLETE_DATA
author: windows-driver-content
description: The WDI_TX_COMPLETE_DATA structure defines TX completion data.
old-location: netvista\wdi_tx_complete_data.htm
old-project: netvista
ms.assetid: bf7951de-3368-4faf-9bae-272c6d76d1a0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_TX_COMPLETE_DATA, *PWDI_TX_COMPLETE_DATA, WDI_TX_COMPLETE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TX_COMPLETE_DATA
req.alt-loc: dot11wdi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDI_TX_COMPLETE_DATA, WDI_TX_COMPLETE_DATA
---

# _WDI_TX_COMPLETE_DATA structure



## -description
The WDI_TX_COMPLETE_DATA structure defines TX completion data.



## -syntax

````
typedef struct _WDI_TX_COMPLETE_DATA {
  UINT16           SeqCtl;
  UINT8            PnLength;
  UINT8            RetryCount;
  UINT16           wPad;
  WDI_TXRX_MPDU_PN MpduPN;
  UINT64           ReplayIHVReserved0;
  UINT64           ReplayIHVReserved1;
} WDI_TX_COMPLETE_DATA, *PWDI_TX_COMPLETE_DATA;
````


## -struct-fields

### -field SeqCtl

The value of the sequence control field from the frame transmission.


### -field PnLength

The MPDU PN length for the transmitted frame.


### -field RetryCount

The number of attempts to transmit the frame.


### -field wPad

This member is reserved.


### -field MpduPN

The MPDU PN.


### -field ReplayIHVReserved0

Reserved for IHV use.


### -field ReplayIHVReserved1

Reserved for IHV use.


## -remarks
