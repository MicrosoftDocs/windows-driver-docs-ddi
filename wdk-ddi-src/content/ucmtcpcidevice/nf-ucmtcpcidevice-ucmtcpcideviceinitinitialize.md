---
UID: NF:ucmtcpcidevice.UcmTcpciDeviceInitInitialize
title: UcmTcpciDeviceInitInitialize function
author: windows-driver-content
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ucmtcpcideviceinitinitialize.htm
old-project: usbref
ms.assetid: a9afbac3-9494-466c-b36b-26a5839913f1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ucmtcpcideviceinitinitialize, ucmtcpcidevice/UcmTcpciDeviceInitInitialize, UcmTcpciDeviceInitInitialize method [Buses], UcmTcpciDeviceInitInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ucmtcpcicxstub.lib
-	ucmtcpcicxstub.dll
apiname:
-	UcmTcpciDeviceInitInitialize
product: Windows
targetos: Windows
req.typenames: UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
req.product: Windows 10 or later.
---

# UcmTcpciDeviceInitInitialize function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

                


## -syntax


````
NTSTATUS UcmTcpciDeviceInitInitialize(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


## -returns



(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



## -remarks


The client driver calls this method after it has performed all of its own initialization in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure, just before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciDeviceInitInitialize method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

