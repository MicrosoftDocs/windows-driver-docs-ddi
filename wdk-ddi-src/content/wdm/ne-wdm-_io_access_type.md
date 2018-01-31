---
UID: NE:wdm._IO_ACCESS_TYPE
title: "_IO_ACCESS_TYPE"
author: windows-driver-content
description: Defines the access rights for Scheduled File I/O (SFIO).
old-location: kernel\io_access_type.htm
old-project: kernel
ms.assetid: 9ABFF1E8-50B8-4B59-964D-BA79AB63BFCE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IO_ACCESS_TYPE enumeration [Kernel-Mode Driver Architecture], wdm/WriteAccess, ReadAccess, WriteAccess, wdm/ReadAccess, _IO_ACCESS_TYPE, kernel.io_access_type, wdm/ModifyAccess, wdm/IO_ACCESS_TYPE, ModifyAccess, IO_ACCESS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	IO_ACCESS_TYPE
product: Windows
targetos: Windows
req.typenames: IO_ACCESS_TYPE
req.product: Windows 10 or later.
---

# _IO_ACCESS_TYPE enumeration


## -description


Defines the access rights for Scheduled File I/O (SFIO).


## -syntax


````
typedef enum _IO_ACCESS_TYPE { 
  ReadAccess,
  WriteAccess,
  ModifyAccess
} IO_ACCESS_TYPE;
````


## -enum-fields




#### - ReadAccess

Indicates that the input/output will be comprised solely of reads.


#### - WriteAccess

Indicates that the input/output will be comprised solely of writes.


#### - ModifyAccess

Indicates that the input/output will be comprised of reads and writes.

