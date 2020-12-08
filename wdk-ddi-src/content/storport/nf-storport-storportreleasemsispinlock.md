---
UID: NF:storport.StorPortReleaseMSISpinLock
title: StorPortReleaseMSISpinLock function (storport.h)
description: The StorPortReleaseMSISpinLock routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message.
old-location: storage\storportreleasemsispinlock.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortReleaseMSISpinLock function"]
ms.keywords: StorPortReleaseMSISpinLock, StorPortReleaseMSISpinLock routine [Storage Devices], storage.storportreleasemsispinlock, storport/StorPortReleaseMSISpinLock, storprt_212b8090-c4a3-4ea8-8c50-6704a6d0cee7.xml
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
 - StorPortReleaseMSISpinLock
 - storport/StorPortReleaseMSISpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortReleaseMSISpinLock
---

# StorPortReleaseMSISpinLock function


## -description

The **StorPortReleaseMSISpinLock** routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param MessageId

The identifier of the message.

### -param OldIrql 

[in]
The IRQL that the [**StorPortAcquireMSISpinLock**](nf-storport-storportacquiremsispinlock.md) routine returned when the miniport driver acquired the spin lock.

## -returns

StorPortReleaseMSISpinLock returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | Indicates that the spin lock was released successfully. |
| **STOR_STATUS_INVALID_PARAMETER** | HwDeviceExtension was **NULL**. |

## -remarks

Miniport drivers are not required to acquire MSI spin locks for messages unless the **InterruptSynchronizePerMessage** member of the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure indicates a synchronization mode of **InterruptSynchronizationMode**.

## -see-also

[**StorPortAcquireMSISpinLock**](nf-storport-storportacquiremsispinlock.md)

