---
UID: NC:storport.HW_BUILDIO
title: HW_BUILDIO (storport.h)
description: The HwStorBuildIo routine processes the SRB with unsynchronized access to shared system data structures before passing it to HwStorStartIo.
old-location: storage\hwstorbuildio.htm
tech.root: storage
ms.assetid: ebbb8289-5996-4d99-98b6-e95fd9dc7ec9
ms.date: 03/29/2018
keywords: ["HW_BUILDIO callback function"]
ms.keywords: HW_BUILDIO, HwStorBuildIo, HwStorBuildIo routine [Storage Devices], storage.hwstorbuildio, stormini_3411fed2-32e6-4a3a-a9c3-0bbe0bb514ca.xml, storport/HwStorBuildIo
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
 - HW_BUILDIO
 - storport/HW_BUILDIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HwStorBuildIo
---

# HW_BUILDIO callback function


## -description

The **HwStorBuildIo** routine processes the SRB with unsynchronized access to shared system data structures before passing it to [**HwStorStartIo**](nc-storport-hw_startio.md).

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

### -param Srb

A pointer to the SCSI request block (SRB) to be processed.

## -returns

**HwStorBuildIo** returns **TRUE** to inform the caller that StorPort should call the [**HwStorStartIo**](nc-storport-hw_startio.md) routine if StorPort considers the LUN ready to receive I/O. **HwStorBuildIo** returns **FALSE** to inform the caller that the SRB should not be passed to **HwStorStartIo**. In such cases, the miniport driver must complete the SRB by calling [**StorPortNotification**](nf-storport-storportnotification.md) with a notification type of **RequestComplete**. This can be done in **HwStorBuildIo** or elsewhere in the miniport driver, as long as the SRB is completed before the timeout that is specified in the **TimeOutValue** field of the SRB structure.

## -remarks

The name **HwStorBuildIo** is just a placeholder for the miniport function that is pointed to by the **HwBuildIo** member in the [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data~r1.md) structure. The actual prototype of this routine is defined in *Storport.h* as follows:

```cpp
typedef
BOOLEAN
HW_BUILDIO (
  _In_ PVOID DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
```

The port driver calls the **HwStorBuildIo** routine at DISPATCH IRQL without holding any spin locks. Because of this, memory allocation using [**StorPortAllocatePool**](nf-storport-storportallocatepool.md) and mutual exclusion via [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md) are allowed in **HwStorBuildIo**. In a multiprocessor environment, more than one **HwStorBuildIo** can be active at a time, so the miniport driver is required to synchronize access to system resources, which may be in contention if more than one instance of  **HwStorBuildIo** is active at any given time.

By completed time-consuming I/O setup activities in **HwStorBuildIo** instead of in [**HwStorStartIo**](nc-storport-hw_startio.md), the miniport driver enables greater I/O concurrency and therefore improves I/O throughput. For highest performance, miniport drivers are expected to do as much preprocessing as possible in **HwStorBuildIo** so that it can send requests to the HBA via **HwStorStartIo** in as short amount of time as possible. Preprocessed data and state can be stored in either the *DeviceExtension* or *SrbExtension* structures. Only modifications to unique portions of the *DeviceExtension* must occur since no locks are held. **HwStorBuildIo** and **HwStorStartIo** receive the following Srb function types:

* SRB_FUNCTION_EXECUTE_SCSI: Sends a CDB to the specified bus/target/lun.
  * Srb->DataTransferLength is valid for all Cdbs.
  * Srb->DataBuffer is **NULL** for read and write requests. To access the associated data, either use [**StorPortGetScatterGatherList**](nf-storport-storportgetscattergatherlist.md) (for Dma transfers) or [**StorPortGetSystemAddress**](nf-storport-storportgetsystemaddress.md) (for program controlled I/O ) to get the Scatter Gather list or the virtual address of the buffer. For other requests, Srb->Databuffer points to the data that is associated with the Srb.
  * Srb->PathId is valid and represents the pathid given to Storport in [**StorPortNotification**](nf-storport-storportnotification.md) (BusChange). Writers of miniport drivers need to use pathid as an index into a table of busses within the miniport.
  * Srb->TargetId and Srb->Lun are valid.

* SRB_FUNCTION_IO_CONTROL: Miniport defined.
  * Srb->DataTransferLength and Srb->DataBuffer are valid if set by the requester.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

* SRB_FUNCTION_RESET_LOGICAL_UNIT: Reset the specified logical unit (if the device is capable).
  * Srb->DataTransferLength and Srb->DataBuffer are invalid.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

* SRB_FUNCTION_RESET_DEVICE: Reset the specified Scsi Target.
  * Srb->DataTransferLength and Srb->DataBuffer, Srb->Lun are invalid.
  * Srb->PathId and Srb->TargetId are valid.

* SRB_FUNCTION_RESET_BUS: Reset all of the targets on the specified SCSI bus.
  * Only Srb->PathId is valid.

* SRB_FUNCTION_FLUSH: Instructs the miniport driver to flush all cached data.
  * Only performed by the miniport driver if it sets **CachesData** == **TRUE** in the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

* SRB_FUNCTION_SHUTDOWN: Instructs the miniport driver to flush all cached data preparatory to shut down.
  * Only performed by the miniport driver if it sets **CachesData** == **TRUE** in the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

* SRB_FUNCTION_DUMP_POINTERS: Supplies information needed for the miniport driver to support crash dump and hibernation.
  * This request is sent to a Storport virtual miniport driver that is used to control the disk that holds the crash dump data. Starting with Windows 8, non-virtual miniport drivers can optionally receive this request.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

* SRB_FUNCTION_FREE_DUMP_POINTERS: Starting with Windows 8, this request is sent to the miniport to free resources allocated during the SRB_FUNCTION_DUMP_POINTERS request.
  * Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

Starting in Windows 8, the *Srb* parameter may point to either [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) or [**STORAGE_REQUEST_BLOCK**](../srb/ns-srb-_storage_request_block.md). If the function identifier in the **Function** field of *Srb* is **SRB_FUNCTION_STORAGE_REQUEST_BLOCK**, the SRB is a **STORAGE_REQUEST_BLOCK** request structure.

For more information about what you can and cannot do safely in this miniport driver routine, see [Unsynchronized HwStorBuildIo Routine](https://docs.microsoft.com/windows-hardware/drivers/storage/unsynchronized-hwstorbuildio-routine).

### Examples

To define an **HwStorBuildIo** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorBuildIo** callback routine that is named *MyHwBuildIo*, use the **HW_BUILDIO** type as shown in this code example:

```cpp
HW_BUILDIO MyHwBuildIo;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
BOOLEAN
MyHwBuildIo (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
  {
      ...
  }
```

The **HW_BUILDIO** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_BUILDIO** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](https://docs.microsoft.com/cpp/code-quality/annotating-function-behavior?view=vs-2019).

## -see-also

[**HwStorStartIo**](nc-storport-hw_startio.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md)

[**STORAGE_REQUEST_BLOCK**](../srb/ns-srb-_storage_request_block.md)

[**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md)

[**StorPortAllocatePool**](nf-storport-storportallocatepool.md)

[**StorPortNotification**](nf-storport-storportnotification.md)

