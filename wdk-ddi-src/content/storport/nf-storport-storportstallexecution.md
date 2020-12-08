---
UID: NF:storport.StorPortStallExecution
title: StorPortStallExecution function (storport.h)
description: The StorPortStallExecution routine stalls the miniport driver.
old-location: storage\storportstallexecution.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortStallExecution function"]
ms.keywords: StorPortStallExecution, StorPortStallExecution routine [Storage Devices], storage.storportstallexecution, storport/StorPortStallExecution, storprt_8cddf62f-d26d-4dd8-85f5-5bf35f74c1de.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortStallExecution
 - storport/StorPortStallExecution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortStallExecution
---

# StorPortStallExecution function


## -description

The <b>StorPortStallExecution</b> routine stalls the miniport driver.

## -parameters

### -param Delay 

[in]
Specifies the delay interval, in microseconds. The given value must be less than a full millisecond.

## -returns

None

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportstallexecution">ScsiPortStallExecution</a>
