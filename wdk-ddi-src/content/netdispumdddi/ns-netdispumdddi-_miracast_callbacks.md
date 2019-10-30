---
UID: NS:netdispumdddi._MIRACAST_CALLBACKS
title: _MIRACAST_CALLBACKS (netdispumdddi.h)
description: Contains pointers to wireless display (Miracast) runtime callback functions that the Miracast user-mode driver can call.
old-location: display\miracast_callbacks.htm
tech.root: display
ms.assetid: 2168a4d8-a33d-4534-b4e8-126a41e528f5
ms.date: 05/10/2018
ms.keywords: "*PMIRACAST_CALLBACKS, MIRACAST_CALLBACKS, MIRACAST_CALLBACKS structure [Display Devices], PMIRACAST_CALLBACKS, PMIRACAST_CALLBACKS structure pointer [Display Devices], _MIRACAST_CALLBACKS, display.miracast_callbacks, netdispumdddi/MIRACAST_CALLBACKS, netdispumdddi/PMIRACAST_CALLBACKS"
ms.topic: struct
f1_keywords:
 - "netdispumdddi/MIRACAST_CALLBACKS"
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Netdispumdddi.h
api_name:
- MIRACAST_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_CALLBACKS, *PMIRACAST_CALLBACKS
---

# _MIRACAST_CALLBACKS structure


## -description


Contains pointers to wireless display (Miracast) runtime callback functions that the Miracast user-mode driver can call.


## -struct-fields




### -field ReportSessionStatus

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_report_session_status">ReportSessionStatus</a>   function.


### -field MiracastIoControl

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a>   function.


### -field ReportStatistic

A pointer to the    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_report_statistic">ReportStatistic</a> function.


### -field GetNextChunkData

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a>    function.


### -field RegisterForDataRateNotifications

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_register_datarate_notifications">RegisterForDataRateNotifications</a>    function.

