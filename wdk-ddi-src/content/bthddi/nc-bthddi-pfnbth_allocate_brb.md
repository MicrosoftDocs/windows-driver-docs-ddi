---
UID: NC:bthddi.PFNBTH_ALLOCATE_BRB
title: PFNBTH_ALLOCATE_BRB
author: windows-driver-content
description: The BthAllocateBrb function allocates a Bluetooth request block (BRB) of the specified type.
old-location: bltooth\bthallocatebrb.htm
old-project: bltooth
ms.assetid: e1ac9d4c-75e2-4d37-86d7-3c3f1486222e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BthAllocateBrb, BthAllocateBrb callback function [Bluetooth Devices], PFNBTH_ALLOCATE_BRB, bltooth.bthallocatebrb, bth_funcs_db0aa96f-62de-40f5-bcce-2aa7e930af3d.xml, bthddi/BthAllocateBrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	BthAllocateBrb
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# PFNBTH_ALLOCATE_BRB callback


## -description


The 
  <i>BthAllocateBrb</i> function allocates a Bluetooth request block (BRB) of the specified type.


## -parameters




### -param brbType [in]

Specifies a value from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a> enumeration to initialize the BRB
     with.


### -param tag [in]

Specifies a 4-byte 
     pool tag that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.


## -returns



<i>BthAllocateBrb</i> returns a pointer to the newly allocated BRB, or <b>NULL</b> if the system is out of
     memory.




## -remarks



Profile drivers obtain a pointer to the 
    <i>BthAllocateBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



pool tag
 

 

