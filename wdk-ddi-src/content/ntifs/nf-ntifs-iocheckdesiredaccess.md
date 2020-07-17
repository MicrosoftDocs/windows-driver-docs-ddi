---
UID: NF:ntifs.IoCheckDesiredAccess
title: IoCheckDesiredAccess function (ntifs.h)
description: Reserved for system use.
old-location: ifsk\iocheckdesiredaccess.htm
tech.root: ifsk
ms.assetid: ab90ab40-7b45-4658-b11b-cf46f91f8699
ms.date: 05/30/2019
keywords: ["IoCheckDesiredAccess function"]
ms.keywords: IoCheckDesiredAccess, IoCheckDesiredAccess function [Installable File System Drivers], ifsk.iocheckdesiredaccess, ioref_f8879d66-0bad-4c92-b2a3-853b7eb65ac6.xml, ntifs/IoCheckDesiredAccess
f1_keywords:
 - "ntifs/IoCheckDesiredAccess"
 - "IoCheckDesiredAccess"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- IoCheckDesiredAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCheckDesiredAccess function

## -description

The **IoCheckDesiredAccess** routine determines whether the requested access rights to a file can be granted.

## -parameters

### -param DesiredAccess

Pointer to a variable containing a mask that identifies the requested access to the file.

### -param GrantedAccess

Mask value that specifies the access currently granted to the file.

## -returns

**IoCheckDesiredAccess** returns STATUS_SUCCESS if *DesiredAccess* is allowed given the current *GrantedAccess*; otherwise, it returns STATUS_ACCESS_DENIED.

## -see-also

[SeAccessCheck](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seaccesscheck)
