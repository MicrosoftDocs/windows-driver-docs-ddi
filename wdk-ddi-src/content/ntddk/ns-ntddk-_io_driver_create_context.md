---
UID: NS:ntddk._IO_DRIVER_CREATE_CONTEXT
title: IO_DRIVER_CREATE_CONTEXT (ntddk.h)
description: The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the IoCreateFileEx and FltCreateFileEx2 routines.
tech.root: ifsk
ms.date: 12/08/2022
keywords: ["IO_DRIVER_CREATE_CONTEXT structure"]
ms.keywords: "*PIO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT structure [Installable File System Drivers], PIO_DRIVER_CREATE_CONTEXT, PIO_DRIVER_CREATE_CONTEXT structure pointer [Installable File System Drivers], _IO_DRIVER_CREATE_CONTEXT, fileinformationstructures_d5939ca3-7c95-4788-bec9-b2d4cc7dd45b.xml, ifsk.io_driver_create_context, ntddk/IO_DRIVER_CREATE_CONTEXT, ntddk/PIO_DRIVER_CREATE_CONTEXT"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.typenames: IO_DRIVER_CREATE_CONTEXT, *PIO_DRIVER_CREATE_CONTEXT
f1_keywords:
 - _IO_DRIVER_CREATE_CONTEXT
 - ntddk/_IO_DRIVER_CREATE_CONTEXT
 - PIO_DRIVER_CREATE_CONTEXT
 - ntddk/PIO_DRIVER_CREATE_CONTEXT
 - IO_DRIVER_CREATE_CONTEXT
 - ntddk/IO_DRIVER_CREATE_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _IO_DRIVER_CREATE_CONTEXT
 - PIO_DRIVER_CREATE_CONTEXT
 - IO_DRIVER_CREATE_CONTEXT
---

## -description

The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) and [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md) routines. This structure is optional.

The [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) routine is used by legacy filter drivers and the [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md) routine is used by minifilter drivers.

## -struct-fields

### -field Size

A read-only member initialized by the [IoInitializeDriverCreateContext](./nf-ntddk-ioinitializedrivercreatecontext.md) routine.

### -field ExtraCreateParameter

A pointer to an [ECP_LIST](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)) structure, which contains a list of extra create parameter (ECP) entries.  See the following **Remarks** section for important information.

### -field DeviceObjectHint

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md) routine, this member must be **NULL**.

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) routine, this member is a pointer to the device object to which the create request will be sent. The device object must be a legacy filter or file system device object in the file system driver stack for the volume on which the file or directory resides. In the **IoCreateFileEx** case, this parameter is optional and can be **NULL**. If this parameter is **NULL**, the request will be sent to the device object at the top of the driver stack.

### -field TxnParameters

A pointer to a transaction that you want to associate with the create operation. The create operation will be part of the transaction if the value of this member is a valid pointer to the transaction. If the value of this member is **NULL**, the create operation will not be part of a transaction.

### -field SiloContext

The container that the file resides on. This member was introduced in Windows 10, version 1607.

## -remarks

The IO_DRIVER_CREATE_CONTEXT structure can be allocated from paged or nonpaged pool. The [IoInitializeDriverCreateContext](./nf-ntddk-ioinitializedrivercreatecontext.md) routine must initialize the IO_DRIVER_CREATE_CONTEXT structure before the structure can be used.

The members of the IO_DRIVER_CREATE_CONTEXT structure (excluding the **Size** member) function as additional parameters to the [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) and [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md) routines.  Relative to the **IoCreateFileEx** and **FltCreateFileEx2** routine's interface, the following information may be helpful:

- An ECP_LIST structure contains a list of extra create parameter (ECP) entries.  Each ECP entry (ECP context structure) in the ECP list (ECP_LIST structure) functions as an additional create parameter to [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) and [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md).

  To specify an ECP as part of a create operation, initialize the **ExtraCreateParameter** member of the IO_DRIVER_CREATE_CONTEXT structure with the correct routine:

  - For legacy filter drivers, the [FsRtlAllocateExtraCreateParameterList](../ntifs/nf-ntifs-fsrtlallocateextracreateparameterlist.md) routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the [FsRtlFreeExtraCreateParameterList](../ntifs/nf-ntifs-fsrtlfreeextracreateparameterlist.md) routine.

  - For minifilter drivers, the [FltAllocateExtraCreateParameterList](../fltkernel/nf-fltkernel-fltallocateextracreateparameterlist.md) routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the [FltFreeExtraCreateParameterList](../fltkernel/nf-fltkernel-fltfreeextracreateparameterlist.md) routine.

  If ECPs are used, they must be created, manipulated, and freed by using the appropriate routines.  For example, minifilter drivers use the [FltInsertExtraCreateParameter](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md) routine to insert an ECP entry into an ECP list.  The following **See Also** section lists many of these required routines.

  Upon return from a call to [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) or [FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md), the ECP list is unchanged and can be passed to additional **IoCreateFileEx** or **FltCreateFileEx2** calls for new create operations.

- To create or open a file in the context of a transaction, set the **TxnParameters** member of the IO_DRIVER_CREATE_CONTEXT structure to the value returned by the [IoGetTransactionParameterBlock](./nf-ntddk-iogettransactionparameterblock.md) routine.  For more information regarding transactions, see [Transaction Management (TxF)](https://go.microsoft.com/fwlink/p/?linkid=66161).

## -see-also

[ECP_LIST](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[FltAllocateExtraCreateParameterFromLookasideList](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[FltAllocateExtraCreateParameterList](../fltkernel/nf-fltkernel-fltallocateextracreateparameterlist.md)

[FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md)

[FltFreeExtraCreateParameter](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[FltFreeExtraCreateParameterList](../fltkernel/nf-fltkernel-fltfreeextracreateparameterlist.md)

[FltGetEcpListFromCallbackData](../fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata.md)

[FltInsertExtraCreateParameter](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md)

[FltRemoveExtraCreateParameter](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

[FltSetEcpListIntoCallbackData](../fltkernel/nf-fltkernel-fltsetecplistintocallbackdata.md)

[FsRtlAllocateExtraCreateParameterList](../ntifs/nf-ntifs-fsrtlallocateextracreateparameterlist.md)

[FsRtlFreeExtraCreateParameterList](../ntifs/nf-ntifs-fsrtlfreeextracreateparameterlist.md)

[IoCreateFileEx](./nf-ntddk-iocreatefileex.md)

[IoCreateFileSpecifyDeviceObjectHint](./nf-ntddk-iocreatefilespecifydeviceobjecthint.md)

[IoGetTransactionParameterBlock](./nf-ntddk-iogettransactionparameterblock.md)

[IoInitializeDriverCreateContext](./nf-ntddk-ioinitializedrivercreatecontext.md)