---
UID: NF:storport.StorPortMoveMemory
title: StorPortMoveMemory function
author: windows-driver-content
description: The StorPortMoveMemory routine copies memory from one buffer to another.
old-location: storage\storportmovememory.htm
old-project: storage
ms.assetid: 5481ae5e-c28a-478e-96be-c6ec8d7f163e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortMoveMemory, StorPortMoveMemory routine [Storage Devices], storage.storportmovememory, storport/StorPortMoveMemory, storprt_7af1ec0d-f1c4-4335-9b80-1aaef26afa35.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortMoveMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortMoveMemory function


## -description


The <b>StorPortMoveMemory</b> routine copies memory from one buffer to another.


## -parameters




### -param WriteBuffer [in]

Pointer to the destination buffer. 


### -param ReadBuffer [in]

Pointer to the source buffer. 


### -param Length [in]

Specifies how many bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>. 


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564654">ScsiPortMoveMemory</a>
 

 

