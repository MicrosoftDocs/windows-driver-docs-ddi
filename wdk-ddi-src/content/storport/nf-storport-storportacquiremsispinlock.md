---
UID: NF:storport.StorPortAcquireMSISpinLock
title: StorPortAcquireMSISpinLock function (storport.h)
description: The StorPortAcquireMSISpinLock routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message.
old-location: storage\storportacquiremsispinlock.htm
tech.root: storage
ms.assetid: 8aa5a8a6-2024-4b3e-a500-5a484d937a62
ms.date: 03/29/2018
keywords: ["StorPortAcquireMSISpinLock function"]
ms.keywords: StorPortAcquireMSISpinLock, StorPortAcquireMSISpinLock routine [Storage Devices], storage.storportacquiremsispinlock, storport/StorPortAcquireMSISpinLock, storprt_0db1ab5c-a2a5-4362-84e0-493a5cebc2d3.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortAcquireMSISpinLock
 - storport/StorPortAcquireMSISpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortAcquireMSISpinLock
---

# StorPortAcquireMSISpinLock function


## -description

The **StorPortAcquireMSISpinLock** routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param MessageId

The identifier of the message whose spin lock the caller acquires.

### -param OldIrql 

[in]
A pointer to the storage for the original IRQL value to be used in a subsequent call to [**StorPortReleaseMSISpinLock**](nf-storport-storportreleasemsispinlock.md).

## -returns

**StorPortAcquireMSISpinLock** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | Indicates that the spin lock was acquired successfully. |
| **STOR_STATUS_INVALID_PARAMETER** | The *HwDeviceExtension* was **NULL**. |

## -remarks

A miniport driver calls the **StorPortAcquireMSISpinLock** routine to acquire the MSI spin lock for a particular message. To release the spin lock, the miniport driver calls the [**StorPortReleaseMSISpinLock**](nf-storport-storportreleasemsispinlock.md) routine. This routine is used by a miniport drivers to acquire a  the MSI spin lock for an individual message only when the **InterruptSynchronizationMode** member of the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure is set to **InterruptSynchronizePerMessage**.

When a miniport needs to synchronize with all messages, it can use one call to [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md) which will acquire a lock for each message in the proper order.

## -see-also

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md)

[**StorPortReleaseMSISpinLock**](nf-storport-storportreleasemsispinlock.md)

