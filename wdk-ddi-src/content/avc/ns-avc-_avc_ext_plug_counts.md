---
UID: NS:avc._AVC_EXT_PLUG_COUNTS
title: "_AVC_EXT_PLUG_COUNTS"
author: windows-driver-content
description: The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit.
old-location: stream\avc_ext_plug_counts.htm
tech.root: stream
ms.assetid: ffae774e-8ec9-49da-bdc6-b56beb45c4c0
ms.date: 4/23/2018
ms.keywords: "*PAVC_EXT_PLUG_COUNTS, AVC_EXT_PLUG_COUNTS, AVC_EXT_PLUG_COUNTS structure [Streaming Media Devices], PAVC_EXT_PLUG_COUNTS, PAVC_EXT_PLUG_COUNTS structure pointer [Streaming Media Devices], _AVC_EXT_PLUG_COUNTS, avc/AVC_EXT_PLUG_COUNTS, avc/PAVC_EXT_PLUG_COUNTS, avcref_171f4765-bb9f-4056-a238-d4822af50a3d.xml, stream.avc_ext_plug_counts"
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	AVC_EXT_PLUG_COUNTS
product:
- Windows
targetos: Windows
req.typenames: AVC_EXT_PLUG_COUNTS, *PAVC_EXT_PLUG_COUNTS
---

# _AVC_EXT_PLUG_COUNTS structure


## -description


The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit.


## -struct-fields




### -field ExtInputs

Ignored on input. On output, this contains the count of external input plugs.


### -field ExtOutputs

Ignored on input. On output, this contains the count of external output plugs.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554145">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554177">AVC_MULTIFUNC_IRB</a>
 

 


