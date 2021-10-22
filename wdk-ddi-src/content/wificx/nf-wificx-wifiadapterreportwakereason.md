---
UID: NF:wificx.WifiAdapterReportWakeReason
tech.root: netvista
title: WifiAdapterReportWakeReason (wificx.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiAdapterReportWakeReason method reports to the framework the reason that a Wi-Fi device has generated a wake-up event.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiAdapterReportWakeReason
f1_keywords:
 - WifiAdapterReportWakeReason
 - wificx/WifiAdapterReportWakeReason
dev_langs:
 - c++
---

## -description

The **WifiAdapterReportWakeReason** method reports to the framework the reason that a Wi-Fi device has generated a wake-up event.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Reason

[_In_] A [**WIFI_WAKE_REASON_TYPE**](ne-wificx-wifi_wake_reason_type.md) value that describes the reason for the wake-up event.

## -remarks

## -see-also

[**WIFI_WAKE_REASON_TYPE**](ne-wificx-wifi_wake_reason_type.md)