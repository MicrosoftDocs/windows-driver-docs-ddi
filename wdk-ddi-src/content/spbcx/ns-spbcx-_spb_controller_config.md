---
UID: NS:spbcx._SPB_CONTROLLER_CONFIG
title: _SPB_CONTROLLER_CONFIG (spbcx.h)
description: The SPB_CONTROLLER_CONFIG structure contains the configuration settings for an SPB controller driver.
old-location: spb\spb_controller_config.htm
tech.root: SPB
ms.assetid: 73856669-ACE9-46B0-AC7A-282D9C8A0285
ms.date: 04/30/2018
ms.keywords: "*PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG structure pointer [Buses], SPB.spb_controller_config, SPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG structure [Buses], _SPB_CONTROLLER_CONFIG, spbcx/PSPB_CONTROLLER_CONFIG, spbcx/SPB_CONTROLLER_CONFIG"
f1_keywords:
 - "spbcx/SPB_CONTROLLER_CONFIG"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Spbcx.h
api_name:
- SPB_CONTROLLER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
---

# _SPB_CONTROLLER_CONFIG structure


## -description


The <b>SPB_CONTROLLER_CONFIG</b> structure contains the configuration settings for an SPB controller driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method uses this parameter value to determine which version of the structure is being used.


### -field ControllerDispatchType

The dispatch type of the I/O queue for the controller driver. Set this member to either <b>WdfIoQueueDispatchSequential</b> or <b>WdfIoQueueDispatchParallel</b>, but not to <b>WdfIoQueueDispatchManual</b>. The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes this member to its default value, <b>WdfIoQueueDispatchSequential</b>. For more information about these dispatch types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/example-uses-of-i-o-queues">Example Uses of I/O Queues</a>.

A controller driver that operates in subordinate mode should set this member to <b>WdfIoQueueDispatchParallel</b>. For example, an I²C controller might be attached as a peripheral device to an SPI bus. This device acts as a master on the I²C bus, but is a subordinate on the SPI bus.


### -field PowerManaged

Whether the I/O queue for the controller driver should be power-managed. Set this member to <b>WdfTrue</b> to indicate that the queue should be power-managed.  Set this member to <b>WdfFalse</b> to indicate that the queue should not be power-managed.  If this member is set to <b>WdfDefault</b>, the queue will be power-managed unless the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetfilter">WdfFdoInitSetFilter</a> method, which identifies the caller as an upper-level or lower-level filter driver. The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes this member to <b>WdfDefault</b>.

When I/O requests are available in a power-managed queue, the framework delivers the requests to the driver only if the device is in its working (D0) state. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/power-management-for-i-o-queues">Power Management for I/O Queues</a>.


### -field EvtSpbTargetConnect

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbTargetConnect</b> member is optional and can be NULL.


### -field EvtSpbTargetDisconnect

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbTargetDisconnect</b> member is optional and can be NULL.


### -field EvtSpbControllerLock

The pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock">EvtSpbControllerLock</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbControllerLock</b> member is optional and can be NULL. For more information about the <i>EvtSpbControllerLock</i> function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/handling-client-implemented-sequences">Handling Client-Implemented Sequences</a>.


### -field EvtSpbControllerUnlock

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a> callback function. This function is implemented by the SPB controller driver. This member is optional and can be NULL. For more information about the <i>EvtSpbControllerUnlock</i> function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/handling-client-implemented-sequences">Handling Client-Implemented Sequences</a>.


### -field EvtSpbIoRead

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


### -field EvtSpbIoWrite

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


### -field EvtSpbIoSequence

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method uses the information in this structure to complete the initialization of the SPB controller.  Before passing this structure to <b>SpbDeviceInitialize</b>, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init">SPB_CONTROLLER_CONFIG_INIT</a> function to initialize the members of this structure to their default values, and, as needed, overwrite these default values with information that is specific to your SPB controller driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock">EvtSpbControllerLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450859">IOCTL_SPB_UNLOCK_CONTROLLER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-write-config">IRP_MN_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init">SPB_CONTROLLER_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetfilter">WdfFdoInitSetFilter</a>
 

 

