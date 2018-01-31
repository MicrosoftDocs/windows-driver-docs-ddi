---
UID: NE:wditypes._WDI_FIPS_MODE
title: "_WDI_FIPS_MODE"
author: windows-driver-content
description: The WDI_FIPS_MODE enumeration defines values that specify if FIPS mode is enabled or not.
old-location: netvista\wdi_fips_mode.htm
old-project: netvista
ms.assetid: 88EE4C63-C9D8-41D2-800E-9FFD5EF4962A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_FIPS_MODE enumeration [Network Drivers Starting with Windows Vista], wditypes/WDI_FIPS_MODE_DISABLED, wditypes/WDI_FIPS_MODE_UNKNOWN, WDI_FIPS_MODE_ENABLED, _WDI_FIPS_MODE, WDI_FIPS_MODE_DISABLED, WDI_FIPS_MODE_UNKNOWN, wditypes/WDI_FIPS_MODE, wditypes/WDI_FIPS_MODE_ENABLED, netvista.wdi_fips_mode, WDI_FIPS_MODE
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
-	WDI_FIPS_MODE
product: Windows
targetos: Windows
req.typenames: WDI_FIPS_MODE
req.product: Windows 10 or later.
---

# _WDI_FIPS_MODE enumeration


## -description


The 
  WDI_FIPS_MODE enumeration defines values that specify if FIPS mode is enabled or not.


## -syntax


````
typedef enum _WDI_FIPS_MODE { 
  WDI_FIPS_MODE_DISABLED  = 0,
  WDI_FIPS_MODE_ENABLED   = 1,
  WDI_FIPS_MODE_UNKNOWN   = 2
} WDI_FIPS_MODE;
````


## -enum-fields




#### - WDI_FIPS_MODE_DISABLED

FIPS mode is disabled.


#### - WDI_FIPS_MODE_ENABLED

FIPS mode is enabled.


#### - WDI_FIPS_MODE_UNKNOWN

Unknown.

