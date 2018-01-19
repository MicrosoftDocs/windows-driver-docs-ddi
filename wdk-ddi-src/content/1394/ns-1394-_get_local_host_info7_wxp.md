---
UID: NS:1394._GET_LOCAL_HOST_INFO7_WXP
title: _GET_LOCAL_HOST_INFO7_WXP
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO7 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request with u.GetLocalHostInformation.nLevel set to GET_HOST_DMA_CAPABILITIES.
old-location: ieee\get_local_host_info7.htm
old-project: IEEE
ms.assetid: 65c4b7d9-dbd8-4f94-b407-1b06543d0b56
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _GET_LOCAL_HOST_INFO7_WXP, *PGET_LOCAL_HOST_INFO7_WXP, GET_LOCAL_HOST_INFO7_WXP, GET_LOCAL_HOST_INFO7, *PGET_LOCAL_HOST_INFO7
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GET_LOCAL_HOST_INFO7
req.alt-loc: 1394.h
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
req.typenames: *PGET_LOCAL_HOST_INFO7_WXP, GET_LOCAL_HOST_INFO7_WXP
---

# _GET_LOCAL_HOST_INFO7_WXP structure



## -description
The GET_LOCAL_HOST_INFO7 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request with <b>u.GetLocalHostInformation.nLevel</b> set to GET_HOST_DMA_CAPABILITIES.



## -syntax

````
typedef struct _GET_LOCAL_HOST_INFO7 {
  ULONG          HostDmaCapabilities;
  ULARGE_INTEGER MaxDmaBufferSize;
} GET_LOCAL_HOST_INFO7, *PGET_LOCAL_HOST_INFO7;
````


## -struct-fields

### -field HostDmaCapabilities

Always set to zero.


### -field MaxDmaBufferSize

Specifies the maximum size of a single DMA transfer on the 1394 host controller. A value of 0x80001000 indicates that there is no specific maximum size. Otherwise, the value of MaxDmaBufferSize reflects the number of Map Registers that are available to the 1394 host controller to map DMA transfers. MaxDmaBufferSize is the upper limit for the size of the buffer that is described in a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff537401">ISOCH_DESCRIPTOR</a>.


## -remarks
