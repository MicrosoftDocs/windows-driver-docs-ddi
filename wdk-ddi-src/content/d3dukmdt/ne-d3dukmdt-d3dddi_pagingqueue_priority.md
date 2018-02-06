---
UID: NE:d3dukmdt.D3DDDI_PAGINGQUEUE_PRIORITY
title: D3DDDI_PAGINGQUEUE_PRIORITY
author: windows-driver-content
description: The D3DDDI_PAGINGQUEUE_PRIORITY enumeration indicates the scheduling priority relative to other paging queues on a device.
old-location: display\d3dddi_pagingqueue_priority.htm
old-project: display
ms.assetid: A5CF6601-C0BF-4534-93DD-5FFA4F167CFC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddi_pagingqueue_priority, d3dukmdt/D3DDDI_PAGINGQUEUE_PRIORITY_NORMAL, D3DDDI_PAGINGQUEUE_PRIORITY enumeration [Display Devices], D3DDDI_PAGINGQUEUE_PRIORITY_BELOW_NORMAL, d3dukmdt/D3DDDI_PAGINGQUEUE_PRIORITY_BELOW_NORMAL, D3DDDI_PAGINGQUEUE_PRIORITY_ABOVE_NORMAL, d3dukmdt/D3DDDI_PAGINGQUEUE_PRIORITY_ABOVE_NORMAL, D3DDDI_PAGINGQUEUE_PRIORITY_NORMAL, D3DDDI_PAGINGQUEUE_PRIORITY, d3dukmdt/D3DDDI_PAGINGQUEUE_PRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
apiname:
-	D3DDDI_PAGINGQUEUE_PRIORITY
product: Windows
targetos: Windows
req.typenames: D3DDDI_PAGINGQUEUE_PRIORITY
---

# D3DDDI_PAGINGQUEUE_PRIORITY enumeration


## -description


The <b>D3DDDI_PAGINGQUEUE_PRIORITY</b> enumeration indicates the scheduling priority relative to other paging queues on a device.
  


## -syntax


````
typedef enum D3DDDI_PAGINGQUEUE_PRIORITY { 
  D3DDDI_PAGINGQUEUE_PRIORITY_BELOW_NORMAL  = -1,
  D3DDDI_PAGINGQUEUE_PRIORITY_NORMAL        = 0,
  D3DDDI_PAGINGQUEUE_PRIORITY_ABOVE_NORMAL  = 1
} D3DDDI_PAGINGQUEUE_PRIORITY;
````


## -enum-fields




### -field D3DDDI_PAGINGQUEUE_PRIORITY_BELOW_NORMAL

Indicates below normal priority.


### -field D3DDDI_PAGINGQUEUE_PRIORITY_NORMAL

Indicates normal priority.


### -field D3DDDI_PAGINGQUEUE_PRIORITY_ABOVE_NORMAL

Indicates above normal priority.

