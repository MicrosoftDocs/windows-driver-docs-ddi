---
UID: NS:ks.KSMETHOD_ITEM
title: KSMETHOD_ITEM (ks.h)
description: The KSMETHOD_ITEM structure describes a single method within a method set.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSMETHOD_ITEM structure"]
ms.keywords: "*PKSMETHOD_ITEM, KSMETHOD_ITEM, KSMETHOD_ITEM structure [Streaming Media Devices], PKSMETHOD_ITEM, PKSMETHOD_ITEM structure pointer [Streaming Media Devices], ks-struct_e3c7b451-337f-4cc5-a5b8-a28aa9bea679.xml, ks/KSMETHOD_ITEM, ks/PKSMETHOD_ITEM, stream.ksmethod_item"
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
targetos: Windows
req.typenames: KSMETHOD_ITEM, *PKSMETHOD_ITEM
f1_keywords:
 - PKSMETHOD_ITEM
 - ks/PKSMETHOD_ITEM
 - KSMETHOD_ITEM
 - ks/KSMETHOD_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSMETHOD_ITEM
 - KSMETHOD_ITEM
---

## -description

The KSMETHOD_ITEM structure describes a single method within a method set.

## -struct-fields

### -field MethodId

Specifies the identifier of this method within its method set.

### -field MethodHandler

Pointer to a minidriver-supplied [KStrMethodHandler](./nc-ks-pfnkshandler.md) callback routine.

### -field MethodSupported

Specifies if this method is supported or not.

### -field MinMethod

Specifies the minimum size of buffer required to specify the method completely. This size is at least **sizeof**(KSMETHOD) bytes.

### -field MinData

Specifies the minimum size buffer required to specify the method data buffer. This buffer is used to read and/or write information related to the method.

### -field SupportHandler

Pointer to a minidriver-supplied [KStrSupportHandler](/previous-versions/ff567206(v=vs.85)) callback routine.

### -field Flags

Specifies the request type of this method request.

| Value | Type of method request |
|---|---|
| KSMETHOD_TYPE_NONE | Indicates that the *Data* buffer of the handler is not expected to be used. For buffered methods, although space is allocated, no data is copied to or from the system buffer. When in source mode (KSMETHOD_TYPE_SOURCE), no MDL is created. |
| KSMETHOD_TYPE_READ | Indicates that parameters are expected to be read from the *Data* buffer of the handler. When buffered, data is copied to the system buffer. When in source mode, the data is probed and locked for **IoReadAccess**. |
| KSMETHOD_TYPE_WRITE | Indicates that parameters are expected to be written to the *Data* buffer of the handler. When buffered, data is copied from the system buffer. When in source mode, the data is probed and locked for **IoWriteAccess**. |
| KSMETHOD_TYPE_MODIFY | Indicates that parameters are expected to be read and written to the *Data* buffer of the handler. The data passed in is overwritten by the data returned. This might imply that a structure passed in could be merely updated. When buffered, the data is copied to the system buffer, and copied back when the IRP is completed. When in source mode, the data is probed and locked for **IoModifyAccess**. |
| KSMETHOD_TYPE_SOURCE | Indicates that the method is to be processed in source mode. An MDL is allocated and the data is probed and locked. To indicate a buffered method, OR this flag with other flags from this list. |

## -remarks

A minidriver uses the KSMETHOD_ITEM structure to define methods in a method set. The minidriver implements methods and uses the **MethodHandler** member to point to these methods. A client can then use the IOCTL_KS_METHOD request along with the KSMETHOD structure to execute methods on a kernel streaming object that the minidriver handles. For more information, see [KS Methods](/windows-hardware/drivers/stream/ks-methods).

## -see-also

[**KSFASTMETHOD_ITEM**](./ns-ks-ksfastmethod_item.md)

[**KSMETHOD**](/windows-hardware/drivers/stream/ksmethod-structure)

[KStrSupportHandler](/previous-versions/ff567206(v=vs.85))