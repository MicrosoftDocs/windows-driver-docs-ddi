---
UID: NS:ndis.BINARY_DATA
title: BINARY_DATA
author: windows-driver-content
description: The BINARY_DATA structure contains the binary data of a named entry in the registry.
old-location: netvista\binary_data.htm
tech.root: netvista
ms.assetid: 2d629905-49aa-4b66-83f3-0aecb72b73ea
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: BINARY_DATA, BINARY_DATA structure [Network Drivers Starting with Windows Vista], ndis/BINARY_DATA, ndis_configuration_ref_50fc50e5-52d2-4e25-a03b-6c581e50fef1.xml, netvista.binary_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	BINARY_DATA
product:
- Windows
targetos: Windows
req.typenames: BINARY_DATA
---

# BINARY_DATA structure


## -description


The BINARY_DATA structure contains the binary data of a named entry in the registry.


## -struct-fields




### -field Length

The length, in bytes, of the data that the 
     <b>Buffer</b> member points to.


### -field Buffer

Pointer to a buffer containing the binary data.


## -remarks



The BINARY_DATA structure is used in the 
    <b>ParameterData</b> member of the 
    <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
    NDIS_CONFIGURATION_PARAMETER</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564868">NDIS_CONFIGURATION_PARAMETER</a>
 

 

