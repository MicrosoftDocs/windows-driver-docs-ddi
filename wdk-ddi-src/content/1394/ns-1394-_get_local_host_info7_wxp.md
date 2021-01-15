---
UID: NS:1394._GET_LOCAL_HOST_INFO7_WXP
title: _GET_LOCAL_HOST_INFO7_WXP (1394.h)
description: The GET_LOCAL_HOST_INFO7 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request with u.GetLocalHostInformation.nLevel set to GET_HOST_DMA_CAPABILITIES.
old-location: ieee\get_local_host_info7.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["GET_LOCAL_HOST_INFO7_WXP structure"]
ms.keywords: "*PGET_LOCAL_HOST_INFO7, *PGET_LOCAL_HOST_INFO7_WXP, 1394/GET_LOCAL_HOST_INFO7, 1394/PGET_LOCAL_HOST_INFO7, 1394stct_6e61e5b9-8961-4a88-9927-143aa24e0648.xml, GET_LOCAL_HOST_INFO7, GET_LOCAL_HOST_INFO7 structure [Buses], GET_LOCAL_HOST_INFO7_W2K, GET_LOCAL_HOST_INFO7_WXP, IEEE.get_local_host_info7, PGET_LOCAL_HOST_INFO7, PGET_LOCAL_HOST_INFO7 structure pointer [Buses], _GET_LOCAL_HOST_INFO7_WXP"
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
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO7_WXP, *PGET_LOCAL_HOST_INFO7_WXP
f1_keywords:
 - _GET_LOCAL_HOST_INFO7_WXP
 - 1394/_GET_LOCAL_HOST_INFO7_WXP
 - PGET_LOCAL_HOST_INFO7_WXP
 - 1394/PGET_LOCAL_HOST_INFO7_WXP
 - GET_LOCAL_HOST_INFO7_WXP
 - 1394/GET_LOCAL_HOST_INFO7_WXP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _GET_LOCAL_HOST_INFO7_WXP
 - PGET_LOCAL_HOST_INFO7_WXP
 - GET_LOCAL_HOST_INFO7_WXP
---

# _GET_LOCAL_HOST_INFO7_WXP structure


## -description

The GET_LOCAL_HOST_INFO7 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request with <b>u.GetLocalHostInformation.nLevel</b> set to GET_HOST_DMA_CAPABILITIES.

## -struct-fields

### -field HostDmaCapabilities

Always set to zero.

### -field MaxDmaBufferSize

Specifies the maximum size of a single DMA transfer on the 1394 host controller. A value of 0x80001000 indicates that there is no specific maximum size. Otherwise, the value of MaxDmaBufferSize reflects the number of Map Registers that are available to the 1394 host controller to map DMA transfers. MaxDmaBufferSize is the upper limit for the size of the buffer that is described in a single <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_isoch_descriptor">ISOCH_DESCRIPTOR</a>.

