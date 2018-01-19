---
UID: NS:windot11._DOT11_WFD_CONFIGURATION_TIMEOUT
title: _DOT11_WFD_CONFIGURATION_TIMEOUT
author: windows-driver-content
description: The DOT11_WFD_CONFIGURATION_TIMEOUT structure contains configuration time-out parameters.
old-location: netvista\dot11_wfd_configuration_timeout.htm
old-project: netvista
ms.assetid: 5432EB69-933A-4080-919F-4131DC4044D0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT, DOT11_WFD_CONFIGURATION_TIMEOUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_CONFIGURATION_TIMEOUT
req.alt-loc: Windot11.h
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
req.typenames: *PDOT11_WFD_CONFIGURATION_TIMEOUT, DOT11_WFD_CONFIGURATION_TIMEOUT
req.product: Windows 10 or later.
---

# _DOT11_WFD_CONFIGURATION_TIMEOUT structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_CONFIGURATION_TIMEOUT {
  UCHAR GOTimeout;
  UCHAR ClientTimeout;
} DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT;
````


## -struct-fields

### -field GOTimeout

The time, in milliseconds, allowed to configure as a Group Owner (GO). The miniport must convert this value to the correct units before including it in a Peer-to-Peer Information Element (P2P IE).


### -field ClientTimeout

The time, in milliseconds, allowed to configure as a client. The miniport must convert this value to the correct units before including it in a P2P IE.


## -remarks
