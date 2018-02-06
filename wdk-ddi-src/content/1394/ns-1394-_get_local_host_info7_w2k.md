---
UID: NS:1394._GET_LOCAL_HOST_INFO7_W2K
title: "_GET_LOCAL_HOST_INFO7_W2K"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO7 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request with u.GetLocalHostInformation.nLevel set to GET_HOST_DMA_CAPABILITIES.
old-location: ieee\get_local_host_info7.htm
old-project: IEEE
ms.assetid: 65c4b7d9-dbd8-4f94-b407-1b06543d0b56
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GET_LOCAL_HOST_INFO7, _GET_LOCAL_HOST_INFO7_W2K, 1394/GET_LOCAL_HOST_INFO7, PGET_LOCAL_HOST_INFO7 structure pointer [Buses], *PGET_LOCAL_HOST_INFO7, *PGET_LOCAL_HOST_INFO7_W2K, IEEE.get_local_host_info7, 1394/PGET_LOCAL_HOST_INFO7, 1394stct_6e61e5b9-8961-4a88-9927-143aa24e0648.xml, PGET_LOCAL_HOST_INFO7, GET_LOCAL_HOST_INFO7_W2K, GET_LOCAL_HOST_INFO7 structure [Buses]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	GET_LOCAL_HOST_INFO7
product: Windows
targetos: Windows
req.typenames: "*PGET_LOCAL_HOST_INFO7_W2K, GET_LOCAL_HOST_INFO7_W2K"
---

# _GET_LOCAL_HOST_INFO7_W2K structure


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


### -field MaxOutstandingXmitRequests

 


### -field MaxOutstandingXmitResponses

 


