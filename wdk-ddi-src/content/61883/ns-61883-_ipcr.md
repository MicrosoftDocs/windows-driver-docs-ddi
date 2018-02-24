---
UID: NS:61883._IPCR
title: "_IPCR"
author: windows-driver-content
description: The IPCR structure contains initialization values for an input plug.
old-location: ieee\ipcr.htm
old-project: IEEE
ms.assetid: 81c89fbc-5d58-4983-b591-765a7818b932
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPCR, _IPCR, PIPCR, IEEE.ipcr, 61883_structures_e7226c37-f3b1-4e57-977a-6fb25c853f19.xml, *PIPCR, 61883/PIPCR, 61883/IPCR, PIPCR structure pointer [Buses], IPCR structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
apiname:
-	IPCR
product: Windows
targetos: Windows
req.typenames: IPCR, *PIPCR
---

# _IPCR structure


## -description


The IPCR structure contains initialization values for an input plug. 


## -syntax


````
typedef struct _IPCR {
  ULONG Reserved0  :16;
  ULONG Channel  :6;
  ULONG Reserved1  :2;
  ULONG PPCCounter  :6;
  ULONG BCCCounter  :1;
  ULONG OnLine  :1;
} IPCR, *PIPCR;
````


## -struct-fields




### -field Reserved0

Reserved. 


### -field Channel

Indicates the channel number that the input plug shall use to transmit the isochronous data flow, for a suspended input plug. For an active input plug it indicates the actual channel number that the input plug uses to transmit the isochronous data flow. For an unconnected input plug it has no meaning.


### -field Reserved1

Reserved. 


### -field PPCCounter

Indicates the number of point-to-point connections to the input plug. 


### -field BCCCounter

Indicates, when one, that there is a broadcast-in connection to the input plug. When zero it indicates that there is no connection. 


### -field OnLine

Indicates, when one, that the corresponding input plug is on-line. When zero it indicates that the input plug is off-line.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537010">AV_PCR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20IPCR structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

