---
UID: NS:dot11wdi._WDI_FRAME_METADATA
title: _WDI_FRAME_METADATA (dot11wdi.h)
description: The WDI_FRAME_METADATA structure defines the frame metadata.
old-location: netvista\wdi_frame_metadata.htm
tech.root: netvista
ms.assetid: 34733e8f-cbe0-4fcd-abcf-6791e298282f
ms.date: 05/02/2018
ms.keywords: "*PWDI_FRAME_METADATA, PWDI_FRAME_METADATA, PWDI_FRAME_METADATA structure pointer [Network Drivers Starting with Windows Vista], WDI_FRAME_METADATA, WDI_FRAME_METADATA structure [Network Drivers Starting with Windows Vista], _WDI_FRAME_METADATA, dot11wdi/PWDI_FRAME_METADATA, dot11wdi/WDI_FRAME_METADATA, netvista.wdi_frame_metadata, netvista.wifi_frame_metadata"
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- dot11wdi.h
api_name:
- WDI_FRAME_METADATA
product:
- Windows
targetos: Windows
req.typenames: WDI_FRAME_METADATA, *PWDI_FRAME_METADATA
---

# _WDI_FRAME_METADATA structure


## -description


The 
  WDI_FRAME_METADATA structure defines the frame metadata.


## -struct-fields




### -field Linkage

Reserved for use by the Microsoft component.


### -field pNBL

Set by the LE on RX path and the UE on TX path when the metadata is associated with an NBL.


### -field FrameID

Filled in by the Microsoft component.


### -field wPad

Padding.


### -field dPad

Padding.


### -field u


### -field u.txMetaData

TX metadata.


### -field u.rxMetaData

RX metadata.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297642">WDI_FRAME_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn926112">WDI_RX_METADATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898195">WDI_TX_METADATA</a>
 

 

