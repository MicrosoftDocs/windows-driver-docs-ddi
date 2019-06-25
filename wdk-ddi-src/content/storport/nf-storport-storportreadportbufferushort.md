---
UID: NF:storport.StorPortReadPortBufferUshort
title: StorPortReadPortBufferUshort macro (storport.h)
description: The StorPortReadPortBufferUshort routine reads a value from a specified port address.
old-location: storage\storportreadportbufferushort.htm
tech.root: storage
ms.assetid: 7b45811c-4e5f-4344-b0b3-15d36b912b5b
ms.date: 03/29/2018
ms.keywords: StorPortReadPortBufferUshort, StorPortReadPortBufferUshort routine [Storage Devices], storage.storportreadportbufferushort, storport/StorPortReadPortBufferUshort, storprt_8bb9a625-864a-4566-a570-87425b6bc9af.xml
ms.topic: macro
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
- StorPortReadPortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadPortBufferUshort macro


## -description


The <b>StorPortReadPortBufferUshort</b> routine reads a value from a specified port address. 


## -parameters


### -param h [in]

A pointer to the hardware device extension.


### -param p [in]

A pointer to the address from which to read. 


### -param b [in]

Pointer to the buffer that receives the data that is read.


### -param c [in]

Number of data items to be read. Each data item has a size of <b>sizeof</b>(USHORT). 


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportreadportbufferushort">ScsiPortReadPortBufferUshort</a>. For a nonbuffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreadportushort">StorPortReadPortUshort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportreadportbufferushort">ScsiPortReadPortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreadportushort">StorPortReadPortUshort</a>
 

 

