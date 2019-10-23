---
UID: NF:storport.StorPortReadRegisterBufferUchar
title: StorPortReadRegisterBufferUchar macro (storport.h)
description: The StorPortReadRegisterBufferUchar routine reads a value from a specified register address.
old-location: storage\storportreadregisterbufferuchar.htm
tech.root: storage
ms.assetid: f633a967-46b5-4532-b372-b9739f2146a2
ms.date: 03/29/2018
ms.keywords: StorPortReadRegisterBufferUchar, StorPortReadRegisterBufferUchar routine [Storage Devices], storage.storportreadregisterbufferuchar, storport/StorPortReadRegisterBufferUchar, storprt_361bfb77-1197-40cb-81ec-fc198e6454e9.xml
ms.topic: macro
f1_keywords:
 - "storport/StorPortReadRegisterBufferUchar"
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
- StorPortReadRegisterBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadRegisterBufferUchar macro


## -description


The <b>StorPortReadRegisterBufferUchar</b> routine reads a value from a specified register address. 


## -parameters




### -param h [in]

A Pointer to the hardware device extension.


### -param r [in]

Pointer to the register where the data is to be read. 


### -param b [in]

A pointer to the buffer that receives the data that is read.


### -param c [in]

Number of data items to be read. Each data item has a size of <b>sizeof</b>(UCHAR). 


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadregisterbufferuchar">ScsiPortReadRegisterBufferUchar</a>. For a nonbuffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadregisteruchar">StorPortReadRegisterUchar</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadregisterbufferuchar">ScsiPortReadRegisterBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadregisteruchar">StorPortReadRegisterUchar</a>
 

 

