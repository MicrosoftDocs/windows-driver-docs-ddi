---
UID: NF:ucxclass.UcxInitializeDeviceInit
title: UcxInitializeDeviceInit function (ucxclass.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\_ucxinitializedeviceinit.htm
tech.root: usbref
ms.assetid: A92A3E2E-1C73-40BD-808A-CBC14404F3E9
ms.date: 05/07/2018
ms.keywords: UcxInitializeDeviceInit, UcxInitializeDeviceInit method [Buses], buses._ucxinitializedeviceinit, ucxclass/UcxInitializeDeviceInit
f1_keywords:
 - "ucxclass/UcxInitializeDeviceInit"
req.header: ucxclass.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ucxclass.h
api_name:
- UcxInitializeDeviceInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxInitializeDeviceInit function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.


## -parameters




### -param DeviceInit [in, out]

A pointer to a framework-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. 


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    




## -remarks



The client driver for the host controller calls this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> implementation before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
 

 

