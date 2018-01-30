---
UID: NS:usbcamdi.USBCAMD_INTERFACE
title: USBCAMD_INTERFACE
author: windows-driver-content
description: The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces.
old-location: stream\usbcamd_interface.htm
old-project: stream
ms.assetid: 864dbe8d-2771-4532-8a50-ed1bf5286658
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.usbcamd_interface, usbcamdi/USBCAMD_INTERFACE, usbcamdi/PUSBCAMD_INTERFACE, *PUSBCAMD_INTERFACE, USBCAMD_INTERFACE, USBCAMD_INTERFACE structure [Streaming Media Devices], usbcmdpr_113d60d6-c353-468a-9c3d-801c76caf7be.xml, PUSBCAMD_INTERFACE, PUSBCAMD_INTERFACE structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbcamdi.h
apiname:
-	USBCAMD_INTERFACE
product: Windows
targetos: Windows
req.typenames: USBCAMD_INTERFACE, *PUSBCAMD_INTERFACE
req.product: Windows 10 or later.
---

# USBCAMD_INTERFACE structure


## -description


The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces.


## -syntax


````
typedef struct {
  INTERFACE                      Interface;
  PFNUSBCAMD_WaitOnDeviceEvent   USBCAMD_WaitOnDeviceEvent;
  PFNUSBCAMD_BulkReadWrite       USBCAMD_BulkReadWrite;
  PFNUSBCAMD_SetVideoFormat      USBCAMD_SetVideoFormat;
  PFNUSBCAMD_SetIsoPipeState     USBCAMD_SetIsoPipeState;
  PFNUSBCAMD_CancelBulkReadWrite USBCAMD_CancelBulkReadWrite;
} USBCAMD_INTERFACE, *PUSBCAMD_INTERFACE;
````


## -struct-fields




### -field Interface

Describes the interface that USBCAMD exports for use by other drivers.


### -field USBCAMD_WaitOnDeviceEvent

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff568638">USBCAMD_WaitOnDeviceEvent</a> service.


### -field USBCAMD_BulkReadWrite

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff568577">USBCAMD_BulkReadWrite</a> service.


### -field USBCAMD_SetVideoFormat

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff568634">USBCAMD_SetVideoFormat</a> service.


### -field USBCAMD_SetIsoPipeState

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff568629">USBCAMD_SetIsoPipeState</a> service.


### -field USBCAMD_CancelBulkReadWrite

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff568580">USBCAMD_CancelBulkReadWrite</a> service.


## -remarks


The camera minidriver may obtain the USBCAMD_INTERFACE entry points at any point after it has received <a href="https://msdn.microsoft.com/library/windows/hardware/ff568182">SRB_INITIALIZATION_COMPLETE</a>. The IRP for acquiring a USBCAMD_INTERFACE is <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> and must be sent at IRQL = PASSIVE_LEVEL. Typically, a camera minidriver obtains the addresses of the USBCAMD_INTERFACE entry points once toward the end of the initialization of the camera minidriver. The members of the USBCAMD_INTERFACE structure are filled with the minidriver's entry points as described in <a href="https://msdn.microsoft.com/39db38a8-8279-4c61-9010-cc6d4767efc2">Acquiring USBCAMD2 Features</a>


<b>USBCAMD_INTERFACE</b> is not supported in the original USBCAMD.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568629">USBCAMD_SetIsoPipeState</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568577">USBCAMD_BulkReadWrite</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568182">SRB_INITIALIZATION_COMPLETE</a>

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568634">USBCAMD_SetVideoFormat</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568580">USBCAMD_CancelBulkReadWrite</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568638">USBCAMD_WaitOnDeviceEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_INTERFACE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

