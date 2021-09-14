---
UID: NS:spbcx._SPB_CONTROLLER_CONFIG
title: _SPB_CONTROLLER_CONFIG (spbcx.h)
description: The SPB_CONTROLLER_CONFIG structure contains the configuration settings for an SPB controller driver.
old-location: spb\spb_controller_config.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["SPB_CONTROLLER_CONFIG structure"]
ms.keywords: "*PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG structure pointer [Buses], SPB.spb_controller_config, SPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG structure [Buses], _SPB_CONTROLLER_CONFIG, spbcx/PSPB_CONTROLLER_CONFIG, spbcx/SPB_CONTROLLER_CONFIG"
req.header: spbcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
f1_keywords:
 - _SPB_CONTROLLER_CONFIG
 - spbcx/_SPB_CONTROLLER_CONFIG
 - PSPB_CONTROLLER_CONFIG
 - spbcx/PSPB_CONTROLLER_CONFIG
 - SPB_CONTROLLER_CONFIG
 - spbcx/SPB_CONTROLLER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spbcx.h
api_name:
 - _SPB_CONTROLLER_CONFIG
 - PSPB_CONTROLLER_CONFIG
 - SPB_CONTROLLER_CONFIG
---

# _SPB_CONTROLLER_CONFIG structure

## -description

The *SPB_CONTROLLER_CONFIG* structure contains the configuration settings for an SPB controller driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure. The [SpbDeviceInitialize](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize) method uses this parameter value to determine which version of the structure is being used.

### -field ControllerDispatchType

The dispatch type of the I/O queue for the controller driver. Set this member to either *WdfIoQueueDispatchSequential* or *WdfIoQueueDispatchParallel*, but not to *WdfIoQueueDispatchManual*. The *SPB_CONTROLLER_CONFIG_INIT* function initializes this member to its default value, *WdfIoQueueDispatchSequential*. For more information about these dispatch types, see [Example Uses of I/O Queues](/windows-hardware/drivers/wdf/example-uses-of-i-o-queues).

A controller driver that operates in subordinate mode should set this member to *WdfIoQueueDispatchParallel*. For example, an I<sup>2</sup>C controller might be attached as a peripheral device to an SPI bus. This device acts as a master on the I<sup>2</sup>C bus, but is a subordinate on the SPI bus.

### -field PowerManaged

Whether the I/O queue for the controller driver should be power-managed. Set this member to *WdfTrue* to indicate that the queue should be power-managed. Set this member to *WdfFalse* to indicate that the queue should not be power-managed. If this member is set to *WdfDefault*, the queue will be power-managed unless the driver calls the [WdfFdoInitSetFilter](/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetfilter) method, which identifies the caller as an upper-level or lower-level filter driver. The *SPB_CONTROLLER_CONFIG_INIT* function initializes this member to *WdfDefault*.

When I/O requests are available in a power-managed queue, the framework delivers the requests to the driver only if the device is in its working (D0) state. For more information, see [Power Management for I/O Queues](/windows-hardware/drivers/wdf/power-management-for-i-o-queues).

### -field EvtSpbTargetConnect

A pointer to the [EvtSpbTargetConnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect) callback function. This function is implemented by the SPB controller driver. The *EvtSpbTargetConnect* member is optional and can be NULL.

### -field EvtSpbTargetDisconnect

A pointer to the [EvtSpbTargetDisconnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect) callback function. This function is implemented by the SPB controller driver. The *EvtSpbTargetDisconnect* member is optional and can be NULL.

### -field EvtSpbControllerLock

The pointer to the [EvtSpbControllerLock](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock) callback function. This function is implemented by the SPB controller driver. The *EvtSpbControllerLock* member is optional and can be NULL. For more information about the *EvtSpbControllerLock* function, see [Handling Client-Implemented Sequences](/windows-hardware/drivers/spb/handling-client-implemented-sequences).

### -field EvtSpbControllerUnlock

A pointer to the [EvtSpbControllerUnlock](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock) callback function. This function is implemented by the SPB controller driver. This member is optional and can be NULL. For more information about the *EvtSpbControllerUnlock* function, see [Handling Client-Implemented Sequences](/windows-hardware/drivers/spb/handling-client-implemented-sequences).

### -field EvtSpbIoRead

A pointer to the [EvtSpbControllerIoRead](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read) callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.

### -field EvtSpbIoWrite

A pointer to the [EvtSpbControllerIoWrite](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write) callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.

### -field EvtSpbIoSequence

A pointer to the [EvtSpbControllerIoSequence](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence) callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.

## -remarks

The [SpbDeviceInitialize](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize) method uses the information in this structure to complete the initialization of the SPB controller. Before passing this structure to *SpbDeviceInitialize*, call the [SPB_CONTROLLER_CONFIG_INIT](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init) function to initialize the members of this structure to their default values, and, as needed, overwrite these default values with information that is specific to your SPB controller driver.

## -see-also

* [EvtSpbControllerIoRead](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read)
* [EvtSpbControllerIoSequence](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence)
* [EvtSpbControllerIoWrite](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write)
* [EvtSpbControllerLock](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock)
* [EvtSpbControllerUnlock](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock)
* [EvtSpbTargetConnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect)
* [EvtSpbTargetDisconnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect)
* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)
* [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)
* [IRP_MN_READ](/windows-hardware/drivers/kernel/irp-mn-read-config)
* [IRP_MN_WRITE](/windows-hardware/drivers/kernel/irp-mn-write-config)
* [SPB_CONTROLLER_CONFIG_INIT](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init)
* [SpbDeviceInitialize](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize)
* [SpbRequestGetParameters](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters)
* [WdfFdoInitSetFilter](/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetfilter)
