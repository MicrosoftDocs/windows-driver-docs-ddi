---
UID: NS:netdispumdddi.MIRACAST_STATISTIC_DATA
title: MIRACAST_STATISTIC_DATA
author: windows-driver-content
description: Contains Miracast statistics data that the user-mode display driver reports to the operating system.
old-location: display\miracast_statistic_data.htm
tech.root: display
ms.assetid: 94D5C260-4076-4DB7-8ED3-E0549A872FEE
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: MIRACAST_STATISTIC_DATA, MIRACAST_STATISTIC_DATA structure [Display Devices], display.miracast_statistic_data, netdispumdddi/MIRACAST_STATISTIC_DATA
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
-	MIRACAST_STATISTIC_DATA
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_STATISTIC_DATA
---

# MIRACAST_STATISTIC_DATA structure


## -description


Contains Miracast statistics data that the user-mode display driver reports to the operating system.


## -struct-fields




### -field StatisticType

The type of statistics data from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265480">MIRACAST_STATISTIC_TYPE</a> enumeration.


### -field EncodeComplete


### -field EncodeComplete.ChunkInfo

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265473">MIRACAST_CHUNK_INFO</a> structure that provides info about an encode chunk that is identified by the <b>ChunkId</b> member.


### -field ChunkSent


### -field ChunkSent.ChunkId

The identifier for this chunk, of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn265472">MIRACAST_CHUNK_ID</a>.


### -field ProtocolEvent


### -field ProtocolEvent.Event

The type of protocol event, given as a value of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265477">MIRACAST_PROTOCOL_EVENT</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265472">MIRACAST_CHUNK_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265473">MIRACAST_CHUNK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265477">MIRACAST_PROTOCOL_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265480">MIRACAST_STATISTIC_TYPE</a>
 

 

