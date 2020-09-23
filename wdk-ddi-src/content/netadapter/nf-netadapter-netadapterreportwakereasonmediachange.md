---
UID: NF:netadapter.NetAdapterReportWakeReasonMediaChange
title: NetAdapterReportWakeReasonMediaChange function (netadapter.h)
author: windows-driver-content
description: The NetAdapterReportWakeReasonMediaChange function reports to the framework that a net adapter generated a wake-up event because of a media change.
tech.root: netvista
ms.assetid: 877cde13-87d8-42e6-bf83-7ff81743bacc
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NetAdapterReportWakeReasonMediaChange function"]
ms.keywords: NetAdapterReportWakeReasonMediaChange
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetAdapterReportWakeReasonMediaChange
 - netadapter/NetAdapterReportWakeReasonMediaChange
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterReportWakeReasonMediaChange
product:
 - Windows
---

# NetAdapterReportWakeReasonMediaChange function


## -description

The **NetAdapterReportWakeReasonMediaChange** function reports to the framework that a net adapter generated a wake-up event because of a media change.

## -parameters

### -param Adapter

A handle to the NETADAPTER object.

### -param Reason

A [**NET_IF_MEDIA_CONNECT_STATE**](/windows/win32/api/ifdef/ne-ifdef-net_if_media_connect_state) value that specifies the network interface connection state that triggered the wake-up event.

## -returns

This function does not return a value.

## -remarks

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_IF_MEDIA_CONNECT_STATE**](/windows/win32/api/ifdef/ne-ifdef-net_if_media_connect_state)