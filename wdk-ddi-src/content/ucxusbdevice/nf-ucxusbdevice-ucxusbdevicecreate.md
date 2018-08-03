---
UID: NF:ucxusbdevice.UcxUsbDeviceCreate
title: UcxUsbDeviceCreate function
author: windows-driver-content
description: Creates a USB device object on the specified controller.
old-location: buses\_ucxusbdevicecreate.htm
tech.root: usbref
ms.assetid: 36883440-805F-4588-AA04-3A7BCBEB6D76
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UcxUsbDeviceCreate, UcxUsbDeviceCreate method [Buses], buses._ucxusbdevicecreate, ucxusbdevice/UcxUsbDeviceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxusbdevice.h
api_name:
-	UcxUsbDeviceCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxUsbDeviceCreate function


## -description


Creates a USB device object on the specified controller.


## -parameters




### -param Controller [in]

A handle to the controller object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


### -param UsbDeviceInit [out]

A pointer to a <b>UCXUSBDEVICE_INIT</b> structure that describes various configuration
        operations for creating the USB device object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the USB device object. 


### -param UsbDevice [out]

A pointer to a variable that receives a handle to the new USB device object.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. The parent of the new USB device object is the parent hub device specified by UCX.

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt187823">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187823">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>
 

 

