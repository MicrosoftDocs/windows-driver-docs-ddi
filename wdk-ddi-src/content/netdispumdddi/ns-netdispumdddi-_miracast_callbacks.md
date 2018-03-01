---
UID: NS:netdispumdddi._MIRACAST_CALLBACKS
title: "_MIRACAST_CALLBACKS"
author: windows-driver-content
description: Contains pointers to wireless display (Miracast) runtime callback functions that the Miracast user-mode driver can call.
old-location: display\miracast_callbacks.htm
old-project: display
ms.assetid: 2168a4d8-a33d-4534-b4e8-126a41e528f5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMIRACAST_CALLBACKS, MIRACAST_CALLBACKS, MIRACAST_CALLBACKS structure [Display Devices], PMIRACAST_CALLBACKS, PMIRACAST_CALLBACKS structure pointer [Display Devices], _MIRACAST_CALLBACKS, display.miracast_callbacks, netdispumdddi/MIRACAST_CALLBACKS, netdispumdddi/PMIRACAST_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Netdispumdddi.h
api_name:
-	MIRACAST_CALLBACKS
product: Windows
targetos: Windows
req.typenames: MIRACAST_CALLBACKS, *PMIRACAST_CALLBACKS
---

# _MIRACAST_CALLBACKS structure


## -description


Contains pointers to wireless display (Miracast) runtime callback functions that the Miracast user-mode driver can call.


## -syntax


````
typedef struct _MIRACAST_CALLBACKS {
  PFN_REPORT_SESSION_STATUS           ReportSessionStatus;
  PFN_MIRACAST_IO_CONTROL             MiracastIoControl;
  PFN_REPORT_STATISTIC                ReportStatistic;
  PFN_GET_NEXT_CHUNK_DATA             GetNextChunkData;
  PFN_REGISTER_DATARATE_NOTIFICATIONS RegisterForDataRateNotifications;
} MIRACAST_CALLBACKS, *PMIRACAST_CALLBACKS;
````


## -struct-fields




### -field ReportSessionStatus

A pointer to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_session_status.md">ReportSessionStatus</a>   function.


### -field MiracastIoControl

A pointer to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a>   function.


### -field ReportStatistic

A pointer to the    <a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_statistic.md">ReportStatistic</a> function.


### -field GetNextChunkData

A pointer to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>    function.


### -field RegisterForDataRateNotifications

A pointer to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_register_datarate_notifications.md">RegisterForDataRateNotifications</a>    function.

