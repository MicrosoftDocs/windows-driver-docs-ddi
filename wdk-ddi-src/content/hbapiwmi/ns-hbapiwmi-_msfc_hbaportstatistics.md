---
UID: NS:hbapiwmi._MSFC_HBAPortStatistics
title: _MSFC_HBAPortStatistics (hbapiwmi.h)
description: The MSFC_HBAPortStatistics structure contains statistics information about a port.
old-location: storage\msfc_hbaportstatistics.htm
tech.root: storage
ms.assetid: 0274b3c7-c17e-45bf-867f-2b0f741b2ecb
ms.date: 03/29/2018
ms.keywords: "*PMSFC_HBAPortStatistics, MSFC_HBAPortStatistics, MSFC_HBAPortStatistics structure [Storage Devices], PMSFC_HBAPortStatistics, PMSFC_HBAPortStatistics structure pointer [Storage Devices], _MSFC_HBAPortStatistics, hbapiwmi/MSFC_HBAPortStatistics, hbapiwmi/PMSFC_HBAPortStatistics, storage.msfc_hbaportstatistics, structs-Fibre_93c56324-f8c5-4d43-815a-40ca9d44350d.xml"
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- MSFC_HBAPortStatistics
product:
- Windows
targetos: Windows
req.typenames: MSFC_HBAPortStatistics, *PMSFC_HBAPortStatistics
---

# _MSFC_HBAPortStatistics structure


## -description


The MSFC_HBAPortStatistics structure contains statistics information about a port.


## -struct-fields




### -field SecondsSinceLastReset

Contains the number of seconds since the statistics were last reset.


### -field TxFrames

Contains the number of total transmitted fibre channel frames across all protocols and classes.


### -field TxWords

Contains the number of total transmitted fibre channel words across all protocols and classes.


### -field RxFrames

Contains the number of received fibre channel frames across all protocols and classes.


### -field RxWords

Contains the number of received fibre channel words across all protocols and classes.


### -field LIPCount

Contains the number of loop initialization primitive sequence (LIP) events that have occurred on a arbitrated loop.


### -field NOSCount

Contains the number of nonoperational state primitive sequence (NOS) events that have occurred on the switched fabric.


### -field ErrorFrames

Contains the number of frames that have been received in error.


### -field DumpedFrames

Contains the number of frames that were lost due to a lack of host buffers available.


### -field LinkFailureCount

Contains the link failure count. 


### -field LossOfSyncCount

Contains the loss of synchronization count. 


### -field LossOfSignalCount

Contains the loss of signal count. 


### -field PrimitiveSeqProtocolErrCount

Contains the primitive sequence protocol error count. 


### -field InvalidTxWordCount

Contains a count of the number of invalid transmissions. 


### -field InvalidCRCCount

Contains a count of the number frames with invalid cyclic redundancy checksums. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562513">MSFC_HBAPortStatistics WMI Class</a>
 

 

