---
UID: NF:storport.StorPortInitializeSpinlock
title: StorPortInitializeSpinlock function (storport.h)
description: The StorPortInitializeSpinLock routine initializes a variable of type STOR_KSPIN_LOCK.
old-location: storage\storportinitializespinlock.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortInitializeSpinlock function"]
ms.keywords: StorPortInitializeSpinlock, StorPortInitializeSpinlock routine [Storage Devices], storage.storportinitializespinlock, storport/StorPortInitializeSpinlock
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.typenames: 
f1_keywords:
 - StorPortInitializeSpinlock
 - storport/StorPortInitializeSpinlock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInitializeSpinlock
---

# StorPortInitializeSpinlock function

## -description

The **StorPortInitializeSpinLock** routine initializes a variable of type **STOR_KSPIN_LOCK**.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Lock

[out] Pointer to a spin lock of type **STOR_KSPIN_LOCK**, for which the caller must provide the storage

## -returns

**StorPortInitializeSpinlock** returns a status code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED   | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS           | The list items were removed successfully or the list is already empty. |

## -remarks

This routine must be called before an initial call to [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md), to any other support routine that requires a spin lock as an argument.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

## -see-also

[**StorPortAcquireMSISpinLock**](nf-storport-storportacquiremsispinlock.md)

[**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md)

[**StorPortReleaseMSISpinLock**](nf-storport-storportreleasemsispinlock.md)

[**StorPortReleaseSpinLock**](nf-storport-storportreleasespinlock.md)
