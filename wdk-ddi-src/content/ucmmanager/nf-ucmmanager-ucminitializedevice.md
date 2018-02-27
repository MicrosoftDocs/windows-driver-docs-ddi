---
UID: NF:ucmmanager.UcmInitializeDevice
title: UcmInitializeDevice function
author: windows-driver-content
description: Initializes the USB connector manager framework extension (UcmCx).
old-location: buses\ucminitializedevice.htm
old-project: usbref
ms.assetid: 9159A6ED-0D85-422D-936A-13D7EC907A7C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcmInitializeDevice, UcmInitializeDevice method [Buses], buses.ucminitializedevice, ucmmanager/UcmInitializeDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmInitializeDevice
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UcmInitializeDevice function


## -description


Initializes the USB connector manager framework extension (UcmCx).


## -syntax


````
NTSTATUS UcmInitializeDevice(
  [in] WDFDEVICE           WdfDevice,
  [in] PUCM_MANAGER_CONFIG  Config
);
````


## -parameters




### -param WdfDevice [in]

A handle to a framework device object that the client driver received in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.


### -param Config [in]

A pointer to a caller-supplied <a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a> structure that is initialized by calling <a href="..\ucmmanager\nf-ucmmanager-ucm_manager_config_init.md">UCM_MANAGER_CONFIG_INIT</a>.


## -returns



<b>UcmInitializeDevice</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



This method initializes UcmCx and allocates resources required, registers for PnP events, and sets up I/O targets. The client driver must call this method in the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a>  implementation.




## -see-also

<a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a>



<a href="..\ucmmanager\nf-ucmmanager-ucm_manager_config_init.md">UCM_MANAGER_CONFIG_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmInitializeDevice method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

