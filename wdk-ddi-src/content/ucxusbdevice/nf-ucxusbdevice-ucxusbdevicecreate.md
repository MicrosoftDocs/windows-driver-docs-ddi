---
UID: NF:ucxusbdevice.UcxUsbDeviceCreate
title: UcxUsbDeviceCreate function
author: windows-driver-content
description: Creates a USB device object on the specified controller.
old-location: buses\_ucxusbdevicecreate.htm
old-project: usbref
ms.assetid: 36883440-805F-4588-AA04-3A7BCBEB6D76
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UcxUsbDeviceCreate method [Buses], UcxUsbDeviceCreate, buses._ucxusbdevicecreate, ucxusbdevice/UcxUsbDeviceCreate
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxusbdevice.h
apiname:
-	UcxUsbDeviceCreate
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxUsbDeviceCreate function


## -description


Creates a USB device object on the specified controller.


## -syntax


````
NTSTATUS UcxUsbDeviceCreate(
  [in]           UCXCONTROLLER          Controller,
  [out]          PUCXUSBDEVICE_INIT     *UsbDeviceInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [out]          UCXUSBDEVICE           *UsbDevice
);
````


## -parameters




### -param Controller [in]

A handle to the controller object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


### -param UsbDeviceInit [out]

A pointer to a <b>UCXUSBDEVICE_INIT</b> structure that describes various configuration
        operations for creating the USB device object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the USB device object. 


### -param UsbDevice [out]

A pointer to a variable that receives a handle to the new USB device object.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> call. The parent of the new USB device object is the parent hub device specified by UCX.

For a code example, see <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>.




## -see-also

<a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxUsbDeviceCreate method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

