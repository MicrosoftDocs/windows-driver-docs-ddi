---
UID: NS:ndisndk._NDIS_NDK_PROVIDER_CHARACTERISTICS
title: "_NDIS_NDK_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_NDK_PROVIDER_CHARACTERISTICS structure specifies NDK provider characteristics.
old-location: netvista\ndis_ndk_provider_characteristics.htm
tech.root: netvista
ms.assetid: 40F07AC8-80F7-4DBC-BDC9-236530B011D4
ms.date: 5/2/2018
ms.keywords: "*PNDIS_NDK_PROVIDER_CHARACTERISTICS, NDIS_NDK_PROVIDER_CHARACTERISTICS, NDIS_NDK_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_PROVIDER_CHARACTERISTICS, PNDIS_NDK_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_PROVIDER_CHARACTERISTICS, ndisndk/NDIS_NDK_PROVIDER_CHARACTERISTICS, ndisndk/PNDIS_NDK_PROVIDER_CHARACTERISTICS, netvista.ndis_ndk_provider_characteristics"
ms.topic: struct
req.header: ndisndk.h
req.include-header: Ndis.h
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
-	ndisndk.h
api_name:
-	NDIS_NDK_PROVIDER_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NDK_PROVIDER_CHARACTERISTICS, *PNDIS_NDK_PROVIDER_CHARACTERISTICS
---

# _NDIS_NDK_PROVIDER_CHARACTERISTICS structure


## -description


The <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure specifies NDK provider characteristics.


## -struct-fields




### -field Header

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure that describes this
     <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure. NDIS sets the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>NDIS sets the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_NDK_PROVIDER_CHARACTERISTICS</b>.</li>
<li>NDIS sets the <b>Revision</b> member to <b>NDIS_NDK_PROVIDER_CHARACTERISTICS_REVISION_1</b>.</li>
<li>NDIS sets the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_PROVIDER_CHARACTERISTICS_REVISION_1</b>.</li>
</ul>

### -field Flags

Reserved, must be set to zero.


### -field OpenNDKAdapterHandler

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a> function.


### -field CloseNDKAdapterHandler

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439355">CLOSE_NDK_ADAPTER_HANDLER</a> function.


## -remarks



To specify entry points for NDK services and other NDK provider characteristics, NDIS miniport drivers pass a pointer to an initialized <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439355">CLOSE_NDK_ADAPTER_HANDLER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a>
 

 

