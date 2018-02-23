---
UID: NE:wditypes._WDI_SCAN_TRIGGER
title: "_WDI_SCAN_TRIGGER"
author: windows-driver-content
description: The WDI_SCAN_TRIGGER enumeration defines the scan trigger values.
old-location: netvista\wdi_scan_trigger.htm
old-project: netvista
ms.assetid: 3E201A6D-3A5B-4A6B-8AED-258A96BBF869
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wditypes/WDI_SCAN_TRIGGER_CONNECT, netvista.wdi_scan_trigger, wditypes/WDI_SCAN_TRIGGER_MANUAL, WDI_SCAN_TRIGGER_BACKGROUND, wditypes/WDI_SCAN_TRIGGER, wditypes/WDI_SCAN_TRIGGER_ROAM, wditypes/WDI_SCAN_TRIGGER_FAST_ROAM, WDI_SCAN_TRIGGER_CONNECT, wditypes/WDI_SCAN_TRIGGER_ANQP_QUERY, WDI_SCAN_TRIGGER_MANUAL, WDI_SCAN_TRIGGER enumeration [Device and Driver Installation], WDI_SCAN_TRIGGER, WDI_SCAN_TRIGGER_ROAM, netvista.wifi_scan_trigger, wditypes/WDI_SCAN_TRIGGER_BACKGROUND, _WDI_SCAN_TRIGGER, WDI_SCAN_TRIGGER_ANQP_QUERY, WDI_SCAN_TRIGGER_FAST_ROAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wditypes.hpp
apiname:
-	WDI_SCAN_TRIGGER
product: Windows
targetos: Windows
req.typenames: WDI_SCAN_TRIGGER
req.product: Windows 10 or later.
---

# _WDI_SCAN_TRIGGER enumeration


## -description


The WDI_SCAN_TRIGGER enumeration defines the scan trigger values.


## -syntax


````
typedef enum _WDI_SCAN_TRIGGER { 
  WDI_SCAN_TRIGGER_MANUAL      = 1,
  WDI_SCAN_TRIGGER_BACKGROUND  = 2,
  WDI_SCAN_TRIGGER_ROAM        = 3,
  WDI_SCAN_TRIGGER_CONNECT     = 4,
  WDI_SCAN_TRIGGER_ANQP_QUERY  = 5,
  WDI_SCAN_TRIGGER_FAST_ROAM   = 6
} WDI_SCAN_TRIGGER;
````


## -enum-fields




### -field WDI_SCAN_TRIGGER_MANUAL

The scan was initiated due to a user or application trigger. If this is set, the port must perform a complete scan on all supported channels. 


### -field WDI_SCAN_TRIGGER_BACKGROUND

The scan was initiated due to some background activity. If this is set, the port can perform a complete scan, a partial scan on a subset of supported channels, or no scan.


### -field WDI_SCAN_TRIGGER_ROAM

The scan was initiated for roaming purposes. If the adapter was doing background scans internally and has recent results, it can perform only a subset or no scan. If it does not have recent results, it should perform an appropriate scan.


### -field WDI_SCAN_TRIGGER_CONNECT

The scan was initiated for connecting. This connect may be a first time connect or a connect after a disconnection. The port must always honor this request to perform a scan.


### -field WDI_SCAN_TRIGGER_ANQP_QUERY

The scan was initiated for performing an ANQP query.


### -field WDI_SCAN_TRIGGER_FAST_ROAM

This scan was initiated for roaming purposes, and the host has additional information (for example, neighbor reports or instant connect last channel) to put in specific values in the scan request (such as SSID, BSSID, or band channel).

