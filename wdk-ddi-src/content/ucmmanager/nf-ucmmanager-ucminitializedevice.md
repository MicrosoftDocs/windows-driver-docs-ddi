---
UID: NF:ucmmanager.UcmInitializeDevice
title: UcmInitializeDevice function (ucmmanager.h)
description: Initializes the USB connector manager framework extension (UcmCx).
old-location: buses\ucminitializedevice.htm
tech.root: usbref
ms.assetid: 9159A6ED-0D85-422D-936A-13D7EC907A7C
ms.date: 05/07/2018
keywords: ["UcmInitializeDevice function"]
ms.keywords: UcmInitializeDevice, UcmInitializeDevice method [Buses], buses.ucminitializedevice, ucmmanager/UcmInitializeDevice
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcmInitializeDevice
 - ucmmanager/UcmInitializeDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - UcmCxstub.lib
 - UcmCxstub.dll
api_name:
 - UcmInitializeDevice
---

# UcmInitializeDevice function


## -description

Initializes the USB connector manager framework extension (UcmCx).

## -parameters

### -param WdfDevice 

[in]
A handle to a framework device object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

### -param Config 

[in]
A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_manager_config">UCM_MANAGER_CONFIG</a> structure that is initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_manager_config_init">UCM_MANAGER_CONFIG_INIT</a>.

## -returns

<b>UcmInitializeDevice</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value.

## -remarks

This method initializes UcmCx and allocates resources required, registers for PnP events, and sets up I/O targets. The client driver must call this method in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EVT_WDF_DRIVER_DEVICE_ADD</a>  implementation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_manager_config">UCM_MANAGER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_manager_config_init">UCM_MANAGER_CONFIG_INIT</a>

