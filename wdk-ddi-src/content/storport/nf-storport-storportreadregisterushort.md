---
UID: NF:storport.StorPortReadRegisterUshort
title: StorPortReadRegisterUshort macro
author: windows-driver-content
description: The StorPortReadRegisterUshort routine reads a value from a specified register address.
old-location: storage\storportreadregisterushort.htm
tech.root: storage
ms.assetid: 11659e7d-db54-401c-a179-75cc5d411b55
ms.date: 3/29/2018
ms.keywords: StorPortReadRegisterUshort, StorPortReadRegisterUshort routine [Storage Devices], storage.storportreadregisterushort, storport/StorPortReadRegisterUshort, storprt_f477688d-54cb-4cb6-b713-0e70cfbf2139.xml
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortReadRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadRegisterUshort macro


## -description


The <b>StorPortReadRegisterUshort</b> routine reads a value from a specified register address. 


## -parameters




### -param h [in]

A Pointer to the hardware device extension.



### -param r [in]

A Pointer to the register where the data is to be read. 

## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564744">ScsiPortReadRegisterUshort</a>. For a buffered version of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567481">StorPortReadRegisterBufferUshort</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564744">ScsiPortReadRegisterUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567481">StorPortReadRegisterBufferUshort</a>
 

 

