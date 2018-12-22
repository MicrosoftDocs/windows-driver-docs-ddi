---
UID: NC:bthddi.PFNBTH_REUSE_BRB
title: PFNBTH_REUSE_BRB
description: The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused.
old-location: bltooth\bthreusebrb.htm
tech.root: bltooth
ms.assetid: cdf156a1-1556-441a-ae3d-9a49daf47990
ms.date: 04/27/2018
ms.keywords: BthReuseBrb, BthReuseBrb callback function [Bluetooth Devices], PFNBTH_REUSE_BRB, PFNBTH_REUSE_BRB callback, bltooth.bthreusebrb, bth_funcs_118c4022-448d-4970-ba70-34dcbc488d13.xml, bthddi/BthReuseBrb
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
-	BthReuseBrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNBTH_REUSE_BRB callback function


## -description


The 
  <i>BthReuseBrb</i> function reinitializes a Bluetooth request block (BRB) to be reused.


## -parameters




### -param pBrb [in, out]

Pointer to the BRB to reuse.


### -param brbType [in]

Specifies a value from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a> enumeration to initialize the BRB
     with.


## -returns



None.




## -remarks



Profile drivers obtain a pointer to the 
    <i>BthReuseBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a>
 

 

