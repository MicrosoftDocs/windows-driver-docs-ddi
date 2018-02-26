---
UID: NS:ucmtcpcidevice._UCMTCPCI_DEVICE_CONFIG
title: "_UCMTCPCI_DEVICE_CONFIG"
author: windows-driver-content
description: Used in the client driver's call to UcmTcpciDeviceInitialize. Call UCMTCPCI_DEVICE_CONFIG_INIT to initialize this structure.
old-location: buses\ucmtcpci_device_config.htm
old-project: usbref
ms.assetid: 74de7f2a-8738-472b-8a22-983a82e29fcb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUCMTCPCI_DEVICE_CONFIG, ,, C, D, E, F, G, I, M, N, O, P, PUCMTCPCI_DEVICE_CONFIG, PUCMTCPCI_DEVICE_CONFIG structure pointer [Buses], T, U, UCMTCPCI_DEVICE_CONFIG, UCMTCPCI_DEVICE_CONFIG structure [Buses], V, _, _UCMTCPCI_DEVICE_CONFIG, buses.ucmtcpci_device_config, ucmtcpcidevice/PUCMTCPCI_DEVICE_CONFIG, ucmtcpcidevice/UCMTCPCI_DEVICE_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpcidevice.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpcidevice.h
apiname:
-	UCMTCPCI_DEVICE_CONFIG
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_DEVICE_CONFIG, *PUCMTCPCI_DEVICE_CONFIG
req.product: Windows 10 or later.
---

# _UCMTCPCI_DEVICE_CONFIG structure


## -description



                 Used in the client driver's call to <a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpcideviceinitialize.md">UcmTcpciDeviceInitialize</a>. 
             Call <a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpci_device_config_init.md">UCMTCPCI_DEVICE_CONFIG_INIT</a> to initialize this structure.
             


## -syntax


````
typedef struct _UCMTCPCI_DEVICE_CONFIG {
  ULONG Size;
} UCMTCPCI_DEVICE_CONFIG, *PUCMTCPCI_DEVICE_CONFIG;
````


## -struct-fields




### -field Size

Size of this structure.
                 


## -see-also

<a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpcideviceinitialize.md">UcmTcpciDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_DEVICE_CONFIG structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

