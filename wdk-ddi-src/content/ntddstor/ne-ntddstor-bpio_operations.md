---
UID: NE:ntddstor._BPIO_OPERATIONS
tech.root: storage
title: BPIO_OPERATIONS
ms.date: 07/08/2021
targetos: Windows
description: BPIO_OPERATIONS defines the various BypassIO operations supported by the IOCTL_STORAGE_MANAGE_BYPASS_IO control code.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _BPIO_OPERATIONS
 - BPIO_OPERATIONS
f1_keywords:
 - _BPIO_OPERATIONS
 - ntddstor/_BPIO_OPERATIONS
 - BPIO_OPERATIONS
 - ntddstor/BPIO_OPERATIONS
dev_langs:
 - c++
---

## -description

**BPIO_OPERATIONS** defines the various BypassIO operations supported by the [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) control code.

## -enum-fields

### -field BPIO_OP_ENABLE

Requests that BypassIO be enabled for the given volume or disk (device), which means that a driver might not see all reads/writes for that stack.

> [!NOTE]
> All drivers in the volume and storage stacks have the opportunity to veto the BypassIO enable request, but are encouraged to keep it enabled as much as possible.

On the pre-operation:

* If a driver can support BypassIO for the given device, it should forward the request down the stack.
* If a driver cannot support BypassIO for the given device, it should:
  * Update the [**BPIO_OUTPUT**](ns-ntddstor-bpio_output.md) structure, including the operation NTSTATUS describing why the enable request was vetoed, the driver's name, and a unique, descriptive string with additional details about why it vetoed the enable request.
  * Complete [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) with STATUS_SUCCESS.

During the post-operation, the driver can see if all drivers below it are capable of supporting BypassIO. If yes, the driver should preserve any needed state for the file and continue completion processing. It is the driver's responsibility to maintain state to properly handle requests that might not be compatible with the BypassIO-enabled state.

The file system maintains a per-volume count of how many files have BypassIO currently enabled. The **BPIO_OP_ENABLE** operation is sent only when this count transitions from zero to one.

Even if a volume or storage stack driver vetoes BypassIO, the file system stack can continue to do BypassIO. This is because if someone has vetoed BypassIO on the volume stack, the file system can still bypass filters.

### -field BPIO_OP_DISABLE

Requests that BypassIO be disabled for the given volume/disk. It allows a driver to cleanup any associated BypassIO state.

The file system sends this operation when the last BypassIO-enabled file is disabled or closed (its per-volume count transitions from one to zero).

If a driver receives **BPIO_OP_DISABLE** but does not currently have BypassIO enabled, it should ignore the request.

This operation should not be failed.

### -field BPIO_OP_QUERY

Queries whether BypassIO can be enabled for the given volume or disk.

A storage driver should process this request similar to a **BPIO_OP_ENABLE** operation, filling in the same diagnostic information in the appropriate fields in the [**BPIO_OUTPUT**](ns-ntddstor-bpio_output.md) structure. The major difference is that the driver does not enter the BypassIO ENABLE state during a QUERY.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/stornvme-feature-support/bypassio) for more information.

## -see-also

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md)
