---
UID: NF:ks.KSEVENT_ITEM_IRP_STORAGE
title: KSEVENT_ITEM_IRP_STORAGE macro
author: windows-driver-content
description: This macro retrieves a pointer to the KSEVENT_ITEM structure stored in Irp.
old-location: stream\ksevent_item_irp_storage.htm
old-project: stream
ms.assetid: c23fc5f4-2546-4330-bcdd-8fef59c8219a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksevent_item_irp_storage, KSEVENT_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_ITEM_IRP_STORAGE, KSEVENT_ITEM_IRP_STORAGE, ksfunc_dc3f2f9e-fe47-46ac-9f51-9d07b42e5daf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
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
req.lib: ks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSEVENT_ITEM_IRP_STORAGE
product: Windows
targetos: Windows
req.typenames: 
---

# KSEVENT_ITEM_IRP_STORAGE macro


## -description


This macro retrieves a pointer to the <a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a> structure stored in <i>Irp</i>.


## -syntax


````
 KSEVENT_ITEM_IRP_STORAGE(
    Irp
);
````


## -parameters




### -param Irp


