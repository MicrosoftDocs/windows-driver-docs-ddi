---
UID: NF:ursdevice.UrsDeviceInitInitialize
title: UrsDeviceInitInitialize function
author: windows-driver-content
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ursdeviceinitinitialize.htm
old-project: usbref
ms.assetid: EFA83238-77DF-474D-8F8F-2400C9B23A00
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UrsDeviceInitInitialize, UrsDeviceInitInitialize method [Buses], buses.ursdeviceinitinitialize, ursdevice/UrsDeviceInitInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsDeviceInitInitialize
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UrsDeviceInitInitialize function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.


## -syntax


````
FORCEINLINE NTSTATUS UrsDeviceInitInitialize(
   PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the dual-role controller calls this method in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> implementation before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> and <a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>. For code example, see <b>UrsDeviceInitialize</b>.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



 

 


