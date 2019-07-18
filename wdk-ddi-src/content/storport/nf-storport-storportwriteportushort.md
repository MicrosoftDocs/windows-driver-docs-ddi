---
UID: NF:storport.StorPortWritePortUshort
title: StorPortWritePortUshort macro (storport.h)
description: The StorPortWritePortUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportushort.htm
tech.root: storage
ms.assetid: 7655b6a1-2ed4-4e57-b8b5-e7b8ff2dd1e5
ms.date: 03/29/2018
ms.keywords: StorPortWritePortUshort, StorPortWritePortUshort routine [Storage Devices], storage.storportwriteportushort, storport/StorPortWritePortUshort, storprt_7e675f67-f027-48e7-a41b-b672b0f81d20.xml
ms.topic: macro
f1_keywords:
 - "storport/StorPortWritePortUshort"
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
- StorPortWritePortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortUshort macro


## -description


The <b>StorPortWritePortUshort</b> routine writes a value to a specified register address. 


## -parameters




### -param h

<p>Pointer to the hardware device extension.</p>


### -param p

<p>Contains the address of the port to be written to. </p>


### -param v

<p>Contains the value to be written. </p>






## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportwriteportushort">ScsiPortWritePortUshort</a>. For a buffered equivalent of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportwriteportbufferushort">StorPortWritePortBufferUshort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportwriteportushort">ScsiPortWritePortUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportwriteportbufferushort">StorPortWritePortBufferUshort</a>
 

 

