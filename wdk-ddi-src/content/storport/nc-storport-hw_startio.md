---
UID: NC:storport.HW_STARTIO
title: HW_STARTIO (storport.h)
description: The Storport driver calls the HwStorStartIo routine one time for each incoming I/O request.
old-location: storage\hwstorstartio.htm
tech.root: storage
ms.assetid: 73085ca7-a442-4c16-b1e3-6de048e7f1f7
ms.date: 03/29/2018
keywords: ["HW_STARTIO callback function"]
ms.keywords: HW_STARTIO, HwStorStartIo, HwStorStartIo routine [Storage Devices], storage.hwstorstartio, stormini_8f910467-49f3-4f15-919d-84edee8ad053.xml, storport/HwStorStartIo
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
req.irql: DISPATCH_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_STARTIO
 - storport/HW_STARTIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HwStorStartIo
---

# HW_STARTIO callback function


## -description

The Storport driver calls the **HwStorStartIo** routine one time for each incoming I/O request.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

### -param Srb

A pointer to the SCSI request block to be started.

## -returns

**HwStorStartIo** returns **TRUE** if the request was successfully initiated. Otherwise, it returns **FALSE**.

## -remarks

**HwStorStartIo** initiates an I/O operation. StorPort is designed to use miniport private data that is prepared in [**HwStorBuildIo**](nc-storport-hw_buildio.md) and stored in either the *DeviceExtension* or *Srb->SrbExtension*.  Because **HwStorBuildIo** is called without spin locks, the best driver performance is achieved by preparing as much data  as possible in **HwStorBuildIo**.

Storport calls **HwStorStartIo** in the following ways:

* For [storage non-virtual miniport drivers](https://docs.microsoft.com/windows-hardware/drivers/storage/overview-of-storage-virtual-miniport-drivers), depending on the value of **SynchronizationModel** set in [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md), Storport always calls **HwStorStartIo** the same IRQL and uses an internal spin lock to ensure that I/O requests are initiated sequentially.  The IRQL is either DISPATCH_LEVEL (full-duplex mode) or DIRQL (half-duplex mode).

  When handling I/O in  half-duplex mode, the **HwStorStartIo** routine does not have to acquire its own spin lock. Also, memory allocation using [**StorPortAllocatePool**](nf-storport-storportallocatepool.md) and mutual exclusion via [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md) are not allowed in the **HwStorStartIo** routine. In full-duplex mode, **StorPortAllocatePool** and **StorPortAcquireSpinLock** may be used in the **HwStorStartIo** routine.

  If a non-virtual miniport supports the concurrent channels optimization (STOR_PERF_CONCURRENT_CHANNELS set by [**StorPortInitializePerfOpts**](nf-storport-storportinitializeperfopts.md)), multiple calls to **HwStorStartIo** concurrently are possible. In this case, the miniport will need to ensure that any shared resources are protected by a lock. With this performance optimization, Storport will not acquire the StartIo lock prior to calling **HwStorStartIo** and the miniport must provide its own lock if required.

* For [storage virtual miniport drivers](https://docs.microsoft.com/windows-hardware/drivers/storage/storage-virtual-miniport-drivers), Storport calls **HwStorStartIo** at any IRQL <= DISPATCH_LEVEL and does not use an internal spin lock. The **HwStorStartIo** routine may acquire its own spin lock by calling [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md). Also, calls to [**StorPortAllocatePool**](nf-storport-storportallocatepool.md) are allowed in the **HwStorStartIo** routine of a storage virtual miniport driver.

The SRB is expected to be completed when SCSI status is received. When the Storport driver completes the SRB by calling [**StorPortNotification**](nf-storport-storportnotification.md) with a *NotificationType* of **RequestComplete**, an SRB is expected to return one of the following values in the **SrbStatus** field of the Srb:

* SRB_STATUS_SUCCESS
  * Indicates that the Srb was sent and SCSI status (possibly with data) was returned.
  * Storport returns the data and status to the caller.
  * Miniport action is none, except to complete the request by using [**StorPortNotification**](nf-storport-storportnotification.md) for **RequestComplete**,  probably from the [**HwStorDpcRoutine**](nc-storport-hw_dpc_routine.md).

* SRB_STATUS_BUSY
  * Indicates that there is a temporary problem with sending the Srb (for example, adapter registers or buffers are busy).
  * Storport discards the original Srb and issues a new Srb, including calls to **HwStorBuildIo** and **HwStorStartIo**. All data in the SrbExtension will be lost.
  * Because a new SRB is issued, the miniport must make sure that it never issues SRB_STATUS_BUSY in the middle of a SCSI transaction. After the transaction is started, it must be completed or canceled.  Hardware busy states during the transaction must be handled by the miniport driver.

The name **HwStorStartIo** is a placeholder to describe the miniport routine set in the **HwStartIo** member of [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data~r1.md) structure. This structure is passed in the *HwInitializationData* parameter of [**StorPortInitialize**](nf-storport-storportinitialize.md). The actual prototype of this routine is defined in Storport.h as follows:

```cpp
typedef
BOOLEAN
(*PHW_STARTIO) (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
```

Starting in Windows 8, the *Srb* parameter may point to either [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) or [**STORAGE_REQUEST_BLOCK**](../ddi/srb/ns-srb-_storage_request_block.md). If the function identifier in the **Function** field of *Srb* is **SRB_FUNCTION_STORAGE_REQUEST_BLOCK**, the SRB is a **STORAGE_REQUEST_BLOCK** request structure.

### Examples

To define a **HwStorStartIo** callback routine, you must first provide a function declaration that [Static Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier) (SDV) and other verification tools require, as shown in the following code example:

To define an **HwStorStartIo** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorStartIo** callback routine that is named *MyHwStartIo*, use the **HW_STARTIO** type as shown in this code example:

```cpp
HW_STARTIO MyHwStartIo
```

Then, implement your callback routine as follows:

```cpp
BOOLEAN
MyHwStartIo (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
  {
      ...
  }
```

The **HW_STARTIO** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_STARTIO** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](https://docs.microsoft.com/cpp/code-quality/annotating-function-behavior?view=vs-2019).

## -see-also

[**HwStorBuildIo**](nc-storport-hw_buildio.md)

[**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md)

[**STORAGE_REQUEST_BLOCK**](../srb/ns-srb-_storage_request_block.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)

