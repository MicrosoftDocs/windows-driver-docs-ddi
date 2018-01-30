---
UID: NF:ntifs.FsRtlCompleteRequest
title: FsRtlCompleteRequest macro
author: windows-driver-content
description: The FsRtlCompleteRequest macro completes an IRP with the specified status.
old-location: ifsk\fsrtlcompleterequest.htm
old-project: ifsk
ms.assetid: dd53d3c5-3a31-4ea9-9f16-0d1b9397f63e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlcompleterequest, FsRtlCompleteRequest, FsRtlCompleteRequest function [Installable File System Drivers], ntifs/FsRtlCompleteRequest, fsrtlref_ae47bec7-1534-4ace-a29b-d5b6a5da292c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: ntifs.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlCompleteRequest
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlCompleteRequest macro


## -description


The <b>FsRtlCompleteRequest</b> macro completes an IRP with the specified status.


## -syntax


````
VOID FsRtlCompleteRequest(
  _In_ PIRP     Irp,
  _In_ NTSTATUS Status
);
````


## -parameters




### -param IRP

TBD


### -param STATUS

TBD




#### - Irp [in]

Pointer to the IRP to be completed.


#### - Status [in]

Status value to be returned for the IRP.


## -see-also

<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCompleteRequest function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

