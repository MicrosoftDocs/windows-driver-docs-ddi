---
UID: NF:ntifs.IoSynchronousPageWrite
title: IoSynchronousPageWrite function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iosynchronouspagewrite.htm
old-project: ifsk
ms.assetid: 3d66b517-91cd-44f7-8dfe-853468c49352
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ioref_9ed81b03-18f6-4641-8f4e-b12c4afcfc5d.xml, ntifs/IoSynchronousPageWrite, ifsk.iosynchronouspagewrite, IoSynchronousPageWrite function [Installable File System Drivers], IoSynchronousPageWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	IoSynchronousPageWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoSynchronousPageWrite function


## -description


The <b>IoSynchronousPageWrite</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>, <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>, and <a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>. 


## -syntax


````
  IoSynchronousPageWrite(
    
);
````


## -parameters




### -param FileObject

TBD


### -param MemoryDescriptorList

TBD


### -param StartingOffset

TBD


### -param Event

TBD


### -param IoStatusBlock

TBD





