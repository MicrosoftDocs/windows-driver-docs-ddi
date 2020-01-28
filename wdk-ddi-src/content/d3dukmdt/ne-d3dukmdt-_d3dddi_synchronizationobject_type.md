---
UID: NE:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECT_TYPE
title: _D3DDDI_SYNCHRONIZATIONOBJECT_TYPE (d3dukmdt.h)
description: The D3DDDI_SYNCHRONIZATIONOBJECT_TYPE enumeration indicates the type of synchronization object.
old-location: display\d3dddi_synchronizationobject_type.htm
tech.root: display
ms.assetid: afd1aad4-d4cd-420f-bd3f-f171dc818a3e
ms.date: 05/10/2018
ms.keywords: D3DDDI_CPU_NOTIFICATION, D3DDDI_FENCE, D3DDDI_MONITORED_FENCE, D3DDDI_SEMAPHORE, D3DDDI_SYNCHRONIZATIONOBJECT_TYPE, D3DDDI_SYNCHRONIZATIONOBJECT_TYPE enumeration [Display Devices], D3DDDI_SYNCHRONIZATION_MUTEX, DmEnums_b63edb60-f53f-4779-ad85-b9ad8a889508.xml, _D3DDDI_SYNCHRONIZATIONOBJECT_TYPE, d3dukmdt/, d3dukmdt/D3DDDI_CPU_NOTIFICATION, d3dukmdt/D3DDDI_FENCE, d3dukmdt/D3DDDI_MONITORED_FENCE, d3dukmdt/D3DDDI_SEMAPHORE, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECT_TYPE, d3dukmdt/D3DDDI_SYNCHRONIZATION_MUTEX, display.d3dddi_synchronizationobject_type
f1_keywords:
 - "d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECT_TYPE"
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- D3DDDI_SYNCHRONIZATIONOBJECT_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECT_TYPE
---

# _D3DDDI_SYNCHRONIZATIONOBJECT_TYPE enumeration


## -description


The <b>D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</b> enumeration indicates the type of synchronization object.


## -enum-fields




### -field D3DDDI_SYNCHRONIZATION_MUTEX

The synchronization object is a synchronization mutex.

Supported starting with Windows Vista.


### -field D3DDDI_SEMAPHORE

The synchronization object is a semaphore.

Supported starting with Windows Vista.


### -field D3DDDI_FENCE

The synchronization object is a fence. 

Supported starting with Windows 7.


### -field D3DDDI_CPU_NOTIFICATION

The synchronization object is a CPU notification.

Supported starting with Windows 7.


### -field D3DDDI_MONITORED_FENCE

The synchronization object is a monitored fence.

Supported starting with Windows 10.

The synchronization object is a periodic monitored fence.

Supported starting with Windows 10.


### -field D3DDDI_PERIODIC_MONITORED_FENCE





