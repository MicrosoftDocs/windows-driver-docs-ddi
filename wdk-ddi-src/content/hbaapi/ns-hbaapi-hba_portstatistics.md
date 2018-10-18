---
UID: NS:hbaapi.HBA_PortStatistics
title: HBA_PortStatistics
author: windows-driver-content
description: The HBA_PortStatistics structure contains statistical information about a port.
old-location: storage\hba_portstatistics.htm
tech.root: storage
ms.assetid: 3a0d6633-b4a6-4864-96ae-4f91de11daa1
ms.date: 03/29/2018
ms.keywords: "*PHBA_PORTSTATISTICS, *PSMHBA_FCPHYSTATISTICS, HBA_PORTSTATISTICS, HBA_PORTSTATISTICS structure [Storage Devices], HBA_PortStatistics, HBA_PortStatistics structure [Storage Devices], PHBA_PORTSTATISTICS, PHBA_PORTSTATISTICS structure pointer [Storage Devices], SMHBA_FCPHYSTATISTICS, hbaapi/HBA_PortStatistics, hbaapi/PHBA_PORTSTATISTICS, storage.hba_portstatistics, structs-Fibre_4c6c7237-af5e-415a-a7db-db594b1a5968.xml"
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_PORTSTATISTICS
product:
- Windows
targetos: Windows
req.typenames: HBA_PORTSTATISTICS, *PHBA_PORTSTATISTICS
---

# HBA_PortStatistics structure


## -description


The HBA_PortStatistics structure contains statistical information about a port. 


## -struct-fields




### -field SecondsSinceLastReset

Reports the number of seconds since the statistics were last reset.


### -field TxFrames

Reports the number of fibre channel frames transmitted for all protocols and classes.


### -field TxWords

Reports the number of fibre channel words transmitted for all protocols and classes. 


### -field RxFrames

Reports the number of fibre channel frames received for all protocols and classes. 


### -field RxWords

Reports the number of fibre channel words received for all protocols and classes. 


### -field LIPCount

Reports the number of LIP events that have occurred on a arbitrated loop.


### -field NOSCount

Reports the number of NOS events that have occurred on the switched fabric.


### -field ErrorFrames

Reports the number of frames that have been received in error.


### -field DumpedFrames

Reports the number of frames that were lost due to a lack of host buffers available. 


### -field LinkFailureCount

Reports the link failure count field of the error status block for the port. 


### -field LossOfSyncCount

Reports the value of the loss of synchronization count field of the link error status block for the port.  


### -field LossOfSignalCount

Reports the value of the loss of signal count field of the link error status block for the specified port. 


### -field PrimitiveSeqProtocolErrCount

Reports the value of the primitive sequence protocol error field of the link error status block for the port. 


### -field InvalidTxWordCount

Reports the value of the invalid transmission word field of the link error status block for the specified port. 


### -field InvalidCRCCount

Reports the value of the invalid CRC count field of the link error status block for the specified port. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556107">HBA_GetPortStatistics</a>
 

 

