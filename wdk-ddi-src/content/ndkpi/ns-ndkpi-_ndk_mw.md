---
UID: NS:ndkpi._NDK_MW
title: "_NDK_MW"
author: windows-driver-content
description: The NDK_MW structure specifies the attributes of an NDK memory window (MW) object.
old-location: netvista\ndk_mw.htm
tech.root: netvista
ms.assetid: C304A6AA-6ABA-40DF-8EE1-ABDEBEE3B006
ms.date: 05/02/2018
ms.keywords: NDK_MW, NDK_MW structure [Network Drivers Starting with Windows Vista], PNDK_MW, PNDK_MW structure pointer [Network Drivers Starting with Windows Vista], _NDK_MW, ndkpi/NDK_MW, ndkpi/PNDK_MW, netvista.ndk_mw
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_MW
product:
- Windows
targetos: Windows
req.typenames: NDK_MW
---

# _NDK_MW structure


## -description


The <b>NDK_MW</b> structure specifies the attributes of an NDK memory window (MW) object.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the <b>NDK_MW</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeMw</b>.


### -field Dispatch

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439927">NDK_MW_DISPATCH</a> structure that defines dispatch functions for the NDK MW object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439927">NDK_MW_DISPATCH</a> table before returning the  created MW object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439876">NDK_FN_CREATE_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439927">NDK_MW_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>
 

 

