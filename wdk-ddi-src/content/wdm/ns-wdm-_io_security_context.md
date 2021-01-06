---
UID: NS:wdm._IO_SECURITY_CONTEXT
title: _IO_SECURITY_CONTEXT (wdm.h)
description: The IO_SECURITY_CONTEXT structure represents the security context of an IRP_MJ_CREATE request.
old-location: kernel\io_security_context.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IO_SECURITY_CONTEXT structure"]
ms.keywords: "*PIO_SECURITY_CONTEXT, IO_SECURITY_CONTEXT, IO_SECURITY_CONTEXT structure [Kernel-Mode Driver Architecture], PIO_SECURITY_CONTEXT, PIO_SECURITY_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _IO_SECURITY_CONTEXT, kernel.io_security_context, kstruct_b_2c3ede84-cdd5-4e78-99b9-5ff642463f85.xml, wdm/IO_SECURITY_CONTEXT, wdm/PIO_SECURITY_CONTEXT"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
targetos: Windows
req.typenames: IO_SECURITY_CONTEXT, *PIO_SECURITY_CONTEXT
f1_keywords:
 - _IO_SECURITY_CONTEXT
 - wdm/_IO_SECURITY_CONTEXT
 - PIO_SECURITY_CONTEXT
 - wdm/PIO_SECURITY_CONTEXT
 - IO_SECURITY_CONTEXT
 - wdm/IO_SECURITY_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IO_SECURITY_CONTEXT
---

# _IO_SECURITY_CONTEXT structure


## -description

The <b>IO_SECURITY_CONTEXT</b> structure represents the security context of an <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request.

## -struct-fields

### -field SecurityQos

Reserved for system use.

### -field AccessState

Reserved for use by file systems and file system filter drivers. This member is a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_access_state">ACCESS_STATE</a> structure that contains the object's subject context, granted access types, and remaining desired access types.

### -field DesiredAccess

An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that expresses the access rights that are requested in the <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request.

### -field FullCreateOptions

Reserved for system use.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_access_state">ACCESS_STATE</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>
