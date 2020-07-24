---
UID: NF:ucmtcpcidevice.UcmTcpciDeviceInitInitialize
title: UcmTcpciDeviceInitInitialize function (ucmtcpcidevice.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ucmtcpcideviceinitinitialize.htm
tech.root: usbref
ms.assetid: a9afbac3-9494-466c-b36b-26a5839913f1
ms.date: 05/07/2018
keywords: ["UcmTcpciDeviceInitInitialize function"]
ms.keywords: UcmTcpciDeviceInitInitialize, UcmTcpciDeviceInitInitialize method [Buses], buses.ucmtcpcideviceinitinitialize, ucmtcpcidevice/UcmTcpciDeviceInitInitialize
f1_keywords:
 - "ucmtcpcidevice/UcmTcpciDeviceInitInitialize"
 - "UcmTcpciDeviceInitInitialize"
req.header: ucmtcpcidevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucmtcpcicxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ucmtcpcicxstub.lib
- ucmtcpcicxstub.dll
api_name:
- UcmTcpciDeviceInitInitialize
targetos: Windows
req.typenames: 
---

# UcmTcpciDeviceInitInitialize function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

                


## -parameters




### -param DeviceInit [in]

A pointer to a framework-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. 


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    




## -remarks



The client driver calls this method after it has performed all of its own initialization in the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure, just before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>
 

 

