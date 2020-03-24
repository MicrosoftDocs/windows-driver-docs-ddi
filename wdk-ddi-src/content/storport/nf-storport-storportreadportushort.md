---
UID: NF:storport.StorPortReadPortUshort
title: StorPortReadPortUshort macro (storport.h)
description: The StorPortReadPortUshort routine reads a value from a specified port address.
old-location: storage\storportreadportushort.htm
tech.root: storage
ms.assetid: e5c9e91a-96b7-4774-8bb4-7519968ce072
ms.date: 03/29/2018
keywords: ["StorPortReadPortUshort macro"]
ms.keywords: StorPortReadPortUshort, StorPortReadPortUshort routine [Storage Devices], storage.storportreadportushort, storport/StorPortReadPortUshort, storprt_fe44d011-ae82-4255-9df9-c1d8f999fd63.xml
f1_keywords:
 - "storport/StorPortReadPortUshort"
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
- StorPortReadPortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadPortUshort macro


## -description


The <b>StorPortReadPortUshort</b> routine reads a value from a specified port address. 


## -parameters




### -param h [in]

A pointer to the hardware device extension.


### -param p [in]

A pointer to the address from which to read. 


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferushort">ScsiPortReadPortBufferUshort</a>. For a buffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportbufferushort">StorPortReadPortBufferUshort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferushort">ScsiPortReadPortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportbufferushort">StorPortReadPortBufferUshort</a>
 

 

