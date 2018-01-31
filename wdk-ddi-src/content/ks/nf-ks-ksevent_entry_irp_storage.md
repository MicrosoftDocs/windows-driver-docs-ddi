---
UID: NF:ks.KSEVENT_ENTRY_IRP_STORAGE
title: KSEVENT_ENTRY_IRP_STORAGE macro
author: windows-driver-content
description: This macro retrieves a pointer to the KSEVENT_ENTRY structure stored in Irp.
old-location: stream\ksevent_entry_irp_storage.htm
old-project: stream
ms.assetid: 9d5d30a5-4c87-4651-89e6-0fe4b02e7ea0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSEVENT_ENTRY_IRP_STORAGE macro [Streaming Media Devices], stream.ksevent_entry_irp_storage, ksfunc_174dded2-4521-4d4a-b7ab-13401da80e5b.xml, ks/KSEVENT_ENTRY_IRP_STORAGE, KSEVENT_ENTRY_IRP_STORAGE
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
-	KSEVENT_ENTRY_IRP_STORAGE
product: Windows
targetos: Windows
req.typenames: 
---

# KSEVENT_ENTRY_IRP_STORAGE macro


## -description


This macro retrieves a pointer to the <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure stored in <i>Irp</i>. This information is initialized only for enable requests; it is not initialized for basic support requests. If the event enable is to be handled asynchronously, this storage location must be maintained intact.


## -syntax


````
 KSEVENT_ENTRY_IRP_STORAGE(
    Irp
);
````


## -parameters




#### - Irp


