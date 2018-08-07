---
UID: NF:ks.KSEVENT_SET_IRP_STORAGE
title: KSEVENT_SET_IRP_STORAGE macro
author: windows-driver-content
description: This macro retrieves a pointer to the KSEVENT_SET structure stored in Irp. This information is initialized only for basic support requests; it is not initialized for enable requests.
old-location: stream\ksevent_set_irp_storage.htm
tech.root: stream
ms.assetid: da5ef8dd-2ec1-4728-aef9-05a842f9b5d8
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KSEVENT_SET_IRP_STORAGE, KSEVENT_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_SET_IRP_STORAGE, ksfunc_d0511067-dd15-4e5d-9adf-acc73885a248.xml, stream.ksevent_set_irp_storage
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSEVENT_SET_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSEVENT_SET_IRP_STORAGE macro


## -description


This macro retrieves a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561867">KSEVENT_SET</a> structure stored in <i>Irp</i>. This information is initialized only for basic support requests; it is not initialized for enable requests.


## -parameters




### -param Irp

