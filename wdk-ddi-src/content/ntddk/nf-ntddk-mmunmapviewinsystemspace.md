---
UID: NF:ntddk.MmUnmapViewInSystemSpace
title: MmUnmapViewInSystemSpace function
author: windows-driver-content
description: TBD
ms.assetid: 0fabae76-0497-4d17-a684-fade48708a57
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: MmUnmapViewInSystemSpace
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: "<=(APC_LEVEL)"
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	
api_location: 
-	
api_name: 
-	MmUnmapViewInSystemSpace
product: Windows
targetos: Windows

---

# MmUnmapViewInSystemSpace function


## -description

 The MmUnmapViewInSystemSpace function unmaps the specified section from the system's address space.

## -parameters

### -param MappedBase
Supplies the address of the view to unmap.

## -returns
This function returns true if the map view operation was successful.
## -remarks

## -see-also
[MmMapViewInSystemSpace](nf-ntddk-mmmapviewinsystemspace.md)