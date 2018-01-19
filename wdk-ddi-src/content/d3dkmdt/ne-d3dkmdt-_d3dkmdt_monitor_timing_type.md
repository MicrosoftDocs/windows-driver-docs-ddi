---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_TIMING_TYPE
title: _D3DKMDT_MONITOR_TIMING_TYPE
author: windows-driver-content
description: The D3DKMDT_MONITOR_TIMING_TYPE enumeration is reserved for system use. Do not use it in your driver.
old-location: display\d3dkmdt_monitor_timing_type.htm
old-project: display
ms.assetid: fb8a2c29-f41b-4701-bbc2-f0a8e6dadc11
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_MONITOR_TIMING_TYPE, D3DKMDT_MONITOR_TIMING_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_MONITOR_TIMING_TYPE
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3DKMDT_MONITOR_TIMING_TYPE
---

# _D3DKMDT_MONITOR_TIMING_TYPE enumeration



## -description
The D3DKMDT_MONITOR_TIMING_TYPE enumeration is reserved for system use. Do not use it in your driver.



## -syntax

````
typedef enum _D3DKMDT_MONITOR_TIMING_TYPE { 
  D3DKMDT_MTT_UNINITIALIZED          = 0,
  D3DKMDT_MTT_ESTABLISHED            = 1,
  D3DKMDT_MTT_STANDARD               = 2,
  D3DKMDT_MTT_EXTRASTANDARD          = 3,
  D3DKMDT_MTT_DETAILED               = 4,
  D3DKMDT_MTT_DEFAULTMONITORPROFILE  = 5,
  D3DKMDT_MTT_DRIVER                 = 6
} D3DKMDT_MONITOR_TIMING_TYPE;
````


## -enum-fields

### -field D3DKMDT_MTT_UNINITIALIZED

Reserved for system use.


### -field D3DKMDT_MTT_ESTABLISHED

Reserved for system use.


### -field D3DKMDT_MTT_STANDARD

Reserved for system use.


### -field D3DKMDT_MTT_EXTRASTANDARD

Reserved for system use.


### -field D3DKMDT_MTT_DETAILED

Reserved for system use.


### -field D3DKMDT_MTT_DEFAULTMONITORPROFILE

Reserved for system use.


### -field D3DKMDT_MTT_DRIVER

Reserved for system use.


## -remarks
