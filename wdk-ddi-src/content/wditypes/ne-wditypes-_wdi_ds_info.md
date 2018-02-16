---
UID: NE:wditypes._WDI_DS_INFO
title: "_WDI_DS_INFO"
author: windows-driver-content
description: The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.
old-location: netvista\wdi_ds_info.htm
old-project: netvista
ms.assetid: 4375FF5C-8772-43AB-844B-4AD5E044AF55
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_DS_INFO enumeration [Device and Driver Installation], WDI_DS_CHANGED, netvista.wifi_ds_info, WDI_DS_UNCHANGED, netvista.wdi_ds_info, wditypes/WDI_DS_UNKNOWN, _WDI_DS_INFO, WDI_DS_INFO, wditypes/WDI_DS_INFO, wditypes/WDI_DS_UNCHANGED, wditypes/WDI_DS_CHANGED, WDI_DS_UNKNOWN
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
-	WDI_DS_INFO
product: Windows
targetos: Windows
req.typenames: WDI_DS_INFO
req.product: Windows 10 or later.
---

# _WDI_DS_INFO enumeration


## -description


The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.


## -syntax


````
typedef enum _WDI_DS_INFO { 
  WDI_DS_CHANGED    = 1,
  WDI_DS_UNCHANGED  = 2,
  WDI_DS_UNKNOWN    = 3
} WDI_DS_INFO;
````


## -enum-fields




### -field WDI_DS_CHANGED

New DS.


### -field WDI_DS_UNCHANGED

Same DS as previously associated.


### -field WDI_DS_UNKNOWN

Unable to determine if the DS has changed.


### -field WDI_DS_MAX



