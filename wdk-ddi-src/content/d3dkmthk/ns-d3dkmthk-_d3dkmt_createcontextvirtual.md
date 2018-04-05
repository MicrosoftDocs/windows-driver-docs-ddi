---
UID: NS:d3dkmthk._D3DKMT_CREATECONTEXTVIRTUAL
title: "_D3DKMT_CREATECONTEXTVIRTUAL"
author: windows-driver-content
description: D3DKMT_CREATECONTEXTVIRTUAL is used with D3DKMTCreateContextVirtual to create a kernel mode device context that supports virtual addressing.
old-location: display\d3dkmt_createcontextvirtual.htm
old-project: display
ms.assetid: C9707F47-75DF-4CDE-B88B-24323FC8C94B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CREATECONTEXTVIRTUAL, D3DKMT_CREATECONTEXTVIRTUAL structure [Display Devices], _D3DKMT_CREATECONTEXTVIRTUAL, d3dkmthk/D3DKMT_CREATECONTEXTVIRTUAL, display.d3dkmt_createcontextvirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATECONTEXTVIRTUAL
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CREATECONTEXTVIRTUAL
---

# _D3DKMT_CREATECONTEXTVIRTUAL structure


## -description


<b>D3DKMT_CREATECONTEXTVIRTUAL</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906770">D3DKMTCreateContextVirtual</a> to create a kernel mode device context that supports virtual addressing.




## -struct-fields




### -field hDevice

[in] A handle to the device.


### -field NodeOrdinal

[in] The zero-based index for the node that the context is scheduled on.


### -field EngineAffinity

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544502">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context. 


### -field pPrivateDriverData

[in] A pointer to private data that is passed to a display miniport driver.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field ClientHint

[in] A hint describing which graphics subsystem is creating the context.


### -field hContext

[out] A handle to the context that the <a href="https://msdn.microsoft.com/library/windows/hardware/dn906770">D3DKMTCreateContextVirtual</a> function creates. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544502">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906770">D3DKMTCreateContextVirtual</a>
 

 

