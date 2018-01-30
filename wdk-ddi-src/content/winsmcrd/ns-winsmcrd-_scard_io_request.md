---
UID: NS:winsmcrd._SCARD_IO_REQUEST
title: "_SCARD_IO_REQUEST"
author: windows-driver-content
description: This structure is used to identify a smart card I/O request.
old-location: nfpdrivers\scard_io_request_structure.htm
old-project: nfpdrivers
ms.assetid: DE670712-2F11-4BB0-ADC7-B68C94EF0759
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: SCARD_IO_REQUEST, PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST structure pointer [Near-Field Proximity Drivers], nfpdrivers.scard_io_request_structure, PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, *PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, winsmcrd/PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, _SCARD_IO_REQUEST, winsmcrd/SCARD_IO_REQUEST, SCARD_IO_REQUEST structure [Near-Field Proximity Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsmcrd.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsmcrd.h
apiname:
-	SCARD_IO_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PSCARD_IO_REQUEST, SCARD_IO_REQUEST, *LPSCARD_IO_REQUEST"
req.product: Windows 10 or later.
---

# _SCARD_IO_REQUEST structure


## -description


This structure is used to identify a smart card I/O request.


## -syntax


````
typedef struct _SCARD_IO_REQUEST {
  DWORD  dwProtocol;
  DWORD  cbPciLength;
} SCARD_IO_REQUEST, *PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST;
````


## -struct-fields




### -field dwProtocol

Specifies the protocol ID.


### -field cbPciLength

Specifies the protocol control information length.


## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20SCARD_IO_REQUEST  structure%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

