---
UID: NF:srb.ScsiPortNotification
title: ScsiPortNotification function (srb.h)
description: The ScsiPortNotification routine informs the operating system-specific port driver of certain events, such as when a miniport driver completes a request or is ready to start another SRB, as well as when the HBA indicates certain SCSI error conditions that occurred during an operation.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportnotification.htm
tech.root: storage
ms.date: 01/03/2022
keywords: ["ScsiPortNotification function"]
ms.keywords: ScsiPortNotification, ScsiPortNotification routine [Storage Devices], scsiprt_0e410e4a-e7bb-448b-9d4d-c2a5db63fe02.xml, srb/ScsiPortNotification, storage.scsiportnotification
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: Scsiport.lib; Storport.lib
req.dll: 
req.irql: (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortNotification
 - srb/ScsiPortNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - scsiport.lib
 - scsiport.dll
 - storport.lib
 - storport.dll
api_name:
 - ScsiPortNotification
---

# ScsiPortNotification function

## -description

The **ScsiPortNotification** routine informs the operating system-specific port driver of certain events, such as when a miniport driver completes a request or is ready to start another SRB, as well as when the host bus adapter (HBA) indicates certain SCSI error conditions that occurred during an operation.

> [!NOTE]
>
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param NotificationType

Specifies the type of notification. See Remarks.

### -param HwDeviceExtension

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the **DeviceExtension->HwDeviceExtension** member of the HBA's device object immediately after the miniport driver calls [**ScsiPortInitialize**](nf-srb-scsiportinitialize.md). The port driver frees this memory when it removes the device.

### -param ...

Variadic arguments for this routine. The number and type of arguments depend on **NotificationType**. See Remarks.

## -returns

None

## -remarks

The **ScsiPortNotification** routine has a different set of optional parameters associated with each **NotificationType**. The list of possible values for **NotificationType** follows, along with descriptions for each value.

* **NotificationType = RequestComplete**

  Indicates that the given **Srb** has finished. If this value is set, **ScsiPortNotification** requires one additional parameter: the address of the SRB. After this notification, the operating system-specific port driver owns the request. The miniport driver must not access the **Srb**, and it must not pass the **Srb** to another routine (such as **ScsiPortLogError**).

  Syntax:

  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,   // RequestComplete
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PSCSI_REQUEST_BLOCK    Srb
  );
  ```

* **NotificationType = NextRequest**

  Indicates the miniport driver is ready for another request to a target that is not currently busy. This notification should be sent by the miniport driver as soon as the driver is ready for another request. Usually, this notification is sent from the [**HwScsiStartIo**](/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)) routine but, sometimes, from the [**HwScsiInterrupt**](/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)) (or [**HwScsiEnableInterruptsCallback**](/previous-versions/windows/hardware/drivers/ff557295(v=vs.85))) routine.

* **NotificationType = NextLuRequest**

  Indicates that the HBA is ready for another request for the specified logical unit. If this value is set, **ScsiPortNotification** requires three additional parameters: (1) the path ID, (2) the target ID, and (3) the logical unit number. This value should be used only if the HBA can queue multiple requests and support auto-request sense or tagged queuing.

  Syntax:
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,   // NextLuRequest
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_                        PathId,
    _In_opt_                        TargetId,
    _In_opt_                        Lun
  );
  ```

* **NotificationType = ResetDetected**

  Indicates that the HBA has detected a reset on the SCSI bus. After this notification, the miniport driver is still responsible for completing any active requests. The SCSI port driver will manage all required bus-reset delays.

* **NotificationType = CallEnableInterrupts**

  Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's [**HwScsiEnableInterruptsCallback**](/previous-versions/windows/hardware/drivers/ff557295(v=vs.85)) routine. If this value is set, **ScsiPortNotification** requires an additional parameter: the entry point for the **HwScsiEnableInterruptsCallback**. The miniport driver's [**HwScsiInterrupt**](/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)) routine makes this call *after* disabling interrupts on the HBA, to defer some interrupt-driven I/O processing if the HBA requires polling or stalling in the ISR. While the callback runs, system interrupts remain enabled but the miniport driver's **HwScsiInterrupt** routine will not be called. The **HwScsiEnableInterruptsCallback** is responsible for completing the deferred I/O processing and for calling **ScsiPortNotification** again with **CallDisableInterrupts** and the miniport driver's [**HwScsiDisableInterruptsCallback**](/previous-versions/windows/hardware/drivers/ff557288(v=vs.85)) entry point.

  Syntax:
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,           // CallEnableInterrupts
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PHW_INTERRUPT          HwScsiXxxInterruptsCallback
  );
  ```

* **NotificationType = CallDisableInterrupts**

  Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's **HwScsiDisableInterruptsCallback** routine. If this value is set, **ScsiPortNotification** requires an additional parameter: the entry point for the **HwScsiDisableInterruptsCallback**. While this callback runs, it cannot be preempted by an interrupt except from a device with a higher priority interrupt than the HBA. In this callback, the miniport driver reenables interrupts on the HBA.

  Syntax:
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,          // CallDisableInterrupts
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PHW_INTERRUPT          HwScsiXxxInterruptsCallback
  );
  ```

* **NotificationType = RequestTimerCall**

  Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's [**HwScsiTimer**](/previous-versions/windows/hardware/drivers/ff557327(v=vs.85)) routine in the requested number of microseconds. If this value is set, **ScsiPortNotification** requires two additional parameters: (1) the entry point for the miniport driver's **HwScsiTimer** routine, and (2) a **MiniportTimerValue** interval, in microseconds. Note that the resolution of the system timer is approximately 10 milliseconds.

  Syntax:
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,    // RequestTimerCall
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PHW_TIMER              HwScsiTimer,
    _In_opt_ ULONG                  MiniportTimerValue
  );
  ```

* **NotificationType = BusChangeDetected**

  Indicates that a target device might have been added or removed from a dynamic bus. If this value is set, **ScsiPortNotification** requires an additional parameter: the path ID of the bus on which the change was detected. After this notification, the port driver reenumerates the bus by issuing INQUIRY commands. Bus enumeration is time-consuming and ties up the bus, so a miniport driver should not send this notification unnecessarily.

  Syntax:
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,    // BusChangeDetected
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ UCHAR                  PathId
  );
  ```

* **NotificationType = WMIEvent**

  Indicates that the miniport driver has detected an event for which one or more WMI data consumers is registered. If this value is set, **ScsiPortNotification** requires at least three additional arguments: (1) a pointer to a WMI event structure, (2) the size of the event structure, and (3) the path ID of the target device if the event originated from a device, or 0xFF if the event originated from the adapter. If (3) is a path ID, **ScsiPortNotification** requires two additional arguments: (4) the target ID, and (5) the logical unit number (LUN) of the target device.

  Syntax for PathId != 0xFF
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,    // WMIEvent
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PVOID                  WMIEvent,
    _In_opt_ UCHAR                  PathId,              // != 0xFF
    _In_opt_ UCHAR                  TargetId,
    _In_opt_ UCHAR                  Lun
  );
  ```
  
  Syntax for PathId = 0xFF
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,    // WMIEvent
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ PVOID                  WMIEvent,
    _In_opt_ UCHAR                  PathId               // 0xFF
  );
  ```

* **NotificationType = WMIReregister**

  Indicates that the miniport driver has changed the data items or the number of instances of a given data block previously registered by calling **IoWMIRegistrationControl**. If **WMIReregister** is set, **ScsiPortNotification** requires at least two additional arguments: (1) the path ID of the target device to reregister that device, or 0xFF to reregister the adapter. If (1) is a path ID, **ScsiPortNotification** requires two additional arguments: (2) the target ID, and (3) the logical unit number (LUN) of the target device.

  Syntax for PathId != 0xFF
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,    // WMIReregister
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ UCHAR                  PathId,             // != 0xFF
    _In_opt_ UCHAR                  TargetId,
    _In_opt_ UCHAR                  Lun
  );
  ```
  
  Syntax for PathId = 0xFF
  
  ``` C
  VOID ScsiPortNotification(
    _In_     SCSI_NOTIFICATION_TYPE NotificationType,   // WMIReregister
    _In_     PVOID                  HwDeviceExtension,
    _In_opt_ UCHAR                  PathId              // 0xFF
  );
  ```

Every miniport driver must call **ScsiPortNotification** twice for each call to the miniport driver's [**HwScsiStartIo**](/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)) routine with an SRB that the miniport driver completes successfully. First, the miniport driver calls **ScsiPortNotification** with the **NotificationType** of **NextRequest** or with **NextLuRequest** if the miniport driver supports tagged queuing or multiple requests per LU. Then, the miniport driver calls **ScsiPortNotification** with the **NotificationType** of **RequestComplete** and the request that it has just satisfied.

A miniport driver's **HwScsiInterrupt** routine is most likely to call **ScsiPortNotification** with the **NotificationType** of **ResetDetected**.

If an HBA requires the miniport driver to use more than a millisecond processing interrupt-driven I/O operations, its **HwScsiInterrupt** routine should disable interrupts on the HBA and call **ScsiPortNotification** with **CallEnableInterrupts** and a driver-supplied **HwScsiEnableInterruptsCallback** routine. This routine, in turn, calls **ScsiPortNotification** with **CallDisableInterrupts** and the corresponding driver-supplied **HwScsiDisableInterruptsCallback**.

A miniport driver that is registered as a WMI data provider can call **ScsiPortNotification** with **WMIEvent** to post an event for which it has previously received an enable request. The port driver queues the event in the interrupt data area of the miniport driver's device extension for later processing at a lower IRQL. Because only a limited number of events can be queued at one time, the miniport driver should use **WMIEvent** to signal exceptional rather than routine conditions, and it should give the port driver time to get back to DISPATCH_LEVEL between postings, to prevent events from being lost.

## -see-also

[**HwScsiDisableInterruptsCallback**](/previous-versions/windows/hardware/drivers/ff557288(v=vs.85))

[**HwScsiEnableInterruptsCallback**](/previous-versions/windows/hardware/drivers/ff557295(v=vs.85))

[**HwScsiTimer**](/previous-versions/windows/hardware/drivers/ff557327(v=vs.85))

[**IoWMIRegistrationControl**](../wdm/nf-wdm-iowmiregistrationcontrol.md)

[**ScsiPortCompleteRequest**](nf-srb-scsiportcompleterequest.md)
