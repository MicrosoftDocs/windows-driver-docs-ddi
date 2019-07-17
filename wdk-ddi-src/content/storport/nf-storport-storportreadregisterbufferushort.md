---
UID: NF:storport.StorPortReadRegisterBufferUshort
title: StorPortReadRegisterBufferUshort macro (storport.h)
description: The StorPortReadRegisterBufferUshort routine reads a value from a specified register address.
old-location: storage\storportreadregisterbufferushort.htm
tech.root: storage
ms.assetid: 169f1089-ac17-4d4c-b989-018ff087aa39
ms.date: 03/29/2018
ms.keywords: StorPortReadRegisterBufferUshort, StorPortReadRegisterBufferUshort routine [Storage Devices], storage.storportreadregisterbufferushort, storport/StorPortReadRegisterBufferUshort, storprt_9ba740e5-78b0-464d-903c-6bb4c22788fd.xml
ms.topic: macro
f1_keywords:
 - "storport/StorPortReadRegisterBufferUshort"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortReadRegisterBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadRegisterBufferUshort macro


## -description


The <b>StorPortReadRegisterBufferUshort</b> routine reads a value from a specified register address. 


## -parameters




### -param h [in]

A pointer to the hardware device extension.


### -param r [in]

A pointer to the register where the data is to be read. 


### -param b [in]

A pointer to the buffer that receives the data that is read.


### -param c [in]

The number of data items to be read. Each data item has a size of <b>sizeof</b>(USHORT). 

#### - Register [in]



## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportreadregisterbufferushort">ScsiPortReadRegisterBufferUshort</a>. For a nonbuffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreadregisterushort">StorPortReadRegisterUshort</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportreadregisterbufferushort">ScsiPortReadRegisterBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreadregisterushort">StorPortReadRegisterUshort</a>
 

 

