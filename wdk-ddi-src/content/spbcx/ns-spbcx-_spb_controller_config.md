---
UID: NS:spbcx._SPB_CONTROLLER_CONFIG
title: "_SPB_CONTROLLER_CONFIG"
author: windows-driver-content
description: The SPB_CONTROLLER_CONFIG structure contains the configuration settings for an SPB controller driver.
old-location: spb\spb_controller_config.htm
old-project: SPB
ms.assetid: 73856669-ACE9-46B0-AC7A-282D9C8A0285
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG, PSPB_CONTROLLER_CONFIG structure pointer [Buses], SPB.spb_controller_config, SPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG structure [Buses], _SPB_CONTROLLER_CONFIG, spbcx/PSPB_CONTROLLER_CONFIG, spbcx/SPB_CONTROLLER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Spbcx.h
apiname:
-	SPB_CONTROLLER_CONFIG
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# _SPB_CONTROLLER_CONFIG structure


## -description


The <b>SPB_CONTROLLER_CONFIG</b> structure contains the configuration settings for an SPB controller driver.


## -syntax


````
typedef struct _SPB_CONTROLLER_CONFIG {
  ULONG                       Size;
  WDF_IO_QUEUE_DISPATCH_TYPE  ControllerDispatchType;
  WDF_TRI_STATE               PowerManaged;
  PFN_SPB_TARGET_CONNECT      EvtSpbTargetConnect;
  PFN_SPB_TARGET_DISCONNECT   EvtSpbTargetDisconnect;
  PFN_SPB_CONTROLLER_LOCK     EvtSpbControllerLock;
  PFN_SPB_CONTROLLER_UNLOCK   EvtSpbControllerUnlock;
  PFN_SPB_CONTROLLER_READ     EvtSpbIoRead;
  PFN_SPB_CONTROLLER_WRITE    EvtSpbIoWrite;
  PFN_SPB_CONTROLLER_SEQUENCE EvtSpbIoSequence;
} SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method uses this parameter value to determine which version of the structure is being used.


### -field ControllerDispatchType

The dispatch type of the I/O queue for the controller driver. Set this member to either <b>WdfIoQueueDispatchSequential</b> or <b>WdfIoQueueDispatchParallel</b>, but not to <b>WdfIoQueueDispatchManual</b>. The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes this member to its default value, <b>WdfIoQueueDispatchSequential</b>. For more information about these dispatch types, see <a href="https://msdn.microsoft.com/13b09254-ce0a-4c7d-bdb1-d28ec094a266">Example Uses of I/O Queues</a>.

A controller driver that operates in subordinate mode should set this member to <b>WdfIoQueueDispatchParallel</b>. For example, an I²C controller might be attached as a peripheral device to an SPI bus. This device acts as a master on the I²C bus, but is a subordinate on the SPI bus.


### -field PowerManaged

Whether the I/O queue for the controller driver should be power-managed. Set this member to <b>WdfTrue</b> to indicate that the queue should be power-managed.  Set this member to <b>WdfFalse</b> to indicate that the queue should not be power-managed.  If this member is set to <b>WdfDefault</b>, the queue will be power-managed unless the driver calls the <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a> method, which identifies the caller as an upper-level or lower-level filter driver. The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes this member to <b>WdfDefault</b>.

When I/O requests are available in a power-managed queue, the framework delivers the requests to the driver only if the device is in its working (D0) state. For more information, see <a href="https://msdn.microsoft.com/2e1bf9d2-615b-49b0-b677-f41b23c42eda">Power Management for I/O Queues</a>.


### -field EvtSpbTargetConnect

A pointer to the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbTargetConnect</b> member is optional and can be NULL.


### -field EvtSpbTargetDisconnect

A pointer to the <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbTargetDisconnect</b> member is optional and can be NULL.


### -field EvtSpbControllerLock

The pointer to the <a href="https://msdn.microsoft.com/E08674F1-CE63-464B-9C70-96F93C574753">EvtSpbControllerLock</a> callback function. This function is implemented by the SPB controller driver. The <b>EvtSpbControllerLock</b> member is optional and can be NULL. For more information about the <i>EvtSpbControllerLock</i> function, see <a href="https://msdn.microsoft.com/C1DED853-059D-481F-A524-E50772072018">Handling Client-Implemented Sequences</a>.


### -field EvtSpbControllerUnlock

A pointer to the <a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a> callback function. This function is implemented by the SPB controller driver. This member is optional and can be NULL. For more information about the <i>EvtSpbControllerUnlock</i> function, see <a href="https://msdn.microsoft.com/C1DED853-059D-481F-A524-E50772072018">Handling Client-Implemented Sequences</a>.


### -field EvtSpbIoRead

A pointer to the <a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


### -field EvtSpbIoWrite

A pointer to the <a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


### -field EvtSpbIoSequence

A pointer to the <a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a> callback function. This function is implemented by the SPB controller driver. This member is not optional and must not be NULL.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method uses the information in this structure to complete the initialization of the SPB controller.  Before passing this structure to <b>SpbDeviceInitialize</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406207">SPB_CONTROLLER_CONFIG_INIT</a> function to initialize the members of this structure to their default values, and, as needed, overwrite these default values with information that is specific to your SPB controller driver.




## -see-also

<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450922">SpbRequestGetParameters</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450859">IOCTL_SPB_UNLOCK_CONTROLLER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://msdn.microsoft.com/E08674F1-CE63-464B-9C70-96F93C574753">EvtSpbControllerLock</a>



<a href="https://msdn.microsoft.com/cbc5b959-0aae-4c86-b490-296965a7f158">IRP_MN_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406207">SPB_CONTROLLER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>



<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>



<a href="https://msdn.microsoft.com/d57c30b8-83bd-41c9-906d-b8c95f8ca54e">IRP_MN_WRITE</a>



<a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>



<a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a>



<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_CONTROLLER_CONFIG structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

