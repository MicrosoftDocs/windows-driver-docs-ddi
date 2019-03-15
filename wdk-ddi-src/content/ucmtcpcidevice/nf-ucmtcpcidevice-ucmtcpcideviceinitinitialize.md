---
UID: NF:ucmtcpcidevice.UcmTcpciDeviceInitInitialize
title: UcmTcpciDeviceInitInitialize function (ucmtcpcidevice.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ucmtcpcideviceinitinitialize.htm
tech.root: usbref
ms.assetid: a9afbac3-9494-466c-b36b-26a5839913f1
ms.date: 05/07/2018
ms.keywords: UcmTcpciDeviceInitInitialize, UcmTcpciDeviceInitInitialize method [Buses], buses.ucmtcpcideviceinitinitialize, ucmtcpcidevice/UcmTcpciDeviceInitInitialize
ms.topic: function
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmTcpciDeviceInitInitialize function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

                


## -parameters




### -param DeviceInit [in]

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    




## -remarks



The client driver calls this method after it has performed all of its own initialization in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure, just before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>
 

 

