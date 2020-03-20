---
UID: NF:ursdevice.UrsDeviceInitInitialize
title: UrsDeviceInitInitialize function (ursdevice.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ursdeviceinitinitialize.htm
tech.root: usbref
ms.assetid: EFA83238-77DF-474D-8F8F-2400C9B23A00
ms.date: 05/07/2018
keywords: ["UrsDeviceInitInitialize function"]
ms.keywords: UrsDeviceInitInitialize, UrsDeviceInitInitialize method [Buses], buses.ursdeviceinitinitialize, ursdevice/UrsDeviceInitInitialize
f1_keywords:
 - "ursdevice/UrsDeviceInitInitialize"
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Urscxstub.lib
- Urscxstub.dll
api_name:
- UrsDeviceInitInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# UrsDeviceInitInitialize function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.


## -parameters




### -param DeviceInit

A pointer to a framework-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. 


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -remarks



The client driver for the dual-role controller calls this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> implementation before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>. For code example, see <b>UrsDeviceInitialize</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
 

 

