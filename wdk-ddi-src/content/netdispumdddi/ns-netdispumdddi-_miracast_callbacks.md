---
UID: NS:netdispumdddi._MIRACAST_CALLBACKS
title: "_MIRACAST_CALLBACKS"
description: Contains pointers to wireless display (Miracast) runtime callback functions that the Miracast user-mode driver can call.
old-location: display\miracast_callbacks.htm
tech.root: display
ms.assetid: 2168a4d8-a33d-4534-b4e8-126a41e528f5
ms.date: 05/10/2018
ms.keywords: "*PMIRACAST_CALLBACKS, MIRACAST_CALLBACKS, MIRACAST_CALLBACKS structure [Display Devices], PMIRACAST_CALLBACKS, PMIRACAST_CALLBACKS structure pointer [Display Devices], _MIRACAST_CALLBACKS, display.miracast_callbacks, netdispumdddi/MIRACAST_CALLBACKS, netdispumdddi/PMIRACAST_CALLBACKS"
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

A pointer to the <a href="https://msdn.microsoft.com/a3e44e55-5c6a-4a79-8caa-3a3b9db6b456">ReportSessionStatus</a>   function.


### -field MiracastIoControl

A pointer to the <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a>   function.


### -field ReportStatistic

A pointer to the    <a href="https://msdn.microsoft.com/13e1afa2-5552-468f-ac6b-3458dedd9b76">ReportStatistic</a> function.


### -field GetNextChunkData

A pointer to the <a href="https://msdn.microsoft.com/24b1d89a-4200-41ec-aa73-15b37e4cca6d">GetNextChunkData</a>    function.


### -field RegisterForDataRateNotifications

A pointer to the <a href="https://msdn.microsoft.com/81500bb9-27f1-4688-b244-37dfd766f3c8">RegisterForDataRateNotifications</a>    function.

