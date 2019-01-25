---
UID: NF:ntifs.FsRtlCompleteRequest
title: FsRtlCompleteRequest macro (ntifs.h)
description: The FsRtlCompleteRequest macro completes an IRP with the specified status.
old-location: ifsk\fsrtlcompleterequest.htm
tech.root: ifsk
ms.assetid: dd53d3c5-3a31-4ea9-9f16-0d1b9397f63e
ms.date: 04/16/2018
ms.keywords: FsRtlCompleteRequest, FsRtlCompleteRequest function [Installable File System Drivers], fsrtlref_ae47bec7-1534-4ace-a29b-d5b6a5da292c.xml, ifsk.fsrtlcompleterequest, ntifs/FsRtlCompleteRequest
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlCompleteRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlCompleteRequest macro


## -description


The <b>FsRtlCompleteRequest</b> macro completes an IRP with the specified status.


## -parameters




### -param IRP

<p>Pointer to the IRP to be completed.</p>


### -param STATUS

<p>Status value to be returned for the IRP.</p>






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>
 

 

