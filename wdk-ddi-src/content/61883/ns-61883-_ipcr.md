---
UID: NS:61883._IPCR
title: "_IPCR"
author: windows-driver-content
description: The IPCR structure contains initialization values for an input plug.
old-location: ieee\ipcr.htm
tech.root: IEEE
ms.assetid: 81c89fbc-5d58-4983-b591-765a7818b932
ms.date: 02/15/2018
ms.keywords: "*PIPCR, 61883/IPCR, 61883/PIPCR, 61883_structures_e7226c37-f3b1-4e57-977a-6fb25c853f19.xml, IEEE.ipcr, IPCR, IPCR structure [Buses], PIPCR, PIPCR structure pointer [Buses], _IPCR"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	IPCR
product:
- Windows
targetos: Windows
req.typenames: IPCR, *PIPCR
---

# _IPCR structure


## -description


The IPCR structure contains initialization values for an input plug. 


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
 

 

