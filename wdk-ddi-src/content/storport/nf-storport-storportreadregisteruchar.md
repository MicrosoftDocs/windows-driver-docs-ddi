---
UID: NF:storport.StorPortReadRegisterUchar
title: StorPortReadRegisterUchar macro (storport.h)
description: The StorPortReadRegisterUchar routine reads a value from a specified register address.
old-location: storage\storportreadregisteruchar.htm
tech.root: storage
ms.assetid: 1edf800d-f097-4d3f-ae89-1b11e4f82f2d
ms.date: 03/29/2018
ms.keywords: StorPortReadRegisterUchar, StorPortReadRegisterUchar routine [Storage Devices], storage.storportreadregisteruchar, storport/StorPortReadRegisterUchar, storprt_9f2898e2-6b5e-45ae-9162-57c58a3471f7.xml
ms.topic: macro
f1_keywords:
 - "storport/StorPortReadRegisterUchar"
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
- StorPortReadRegisterUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadRegisterUchar macro


## -description


The <b>StorPortReadRegisterUchar</b> routine reads a value from a specified register address. 


## -parameters




### -param h [in]

A pointer to the hardware device extension.

### -param r [in]

A pointer to the register where the data is to be read. 


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadregisteruchar">ScsiPortReadRegisterUchar</a>. For a buffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadregisterbufferuchar">StorPortReadRegisterBufferUchar</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadregisteruchar">ScsiPortReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadregisterbufferuchar">StorPortReadRegisterBufferUchar</a>
 

 

