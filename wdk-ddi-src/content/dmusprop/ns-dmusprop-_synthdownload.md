---
UID: NS:dmusprop._SYNTHDOWNLOAD
title: "_SYNTHDOWNLOAD"
author: windows-driver-content
description: The SYNTHDOWNLOAD structure specifies a handle for downloaded DLS data. It also specifies whether the buffer containing the DLS data can be freed.
old-location: audio\synthdownload.htm
old-project: audio
ms.assetid: b6fd9c92-ac36-46ac-b996-d76afaf6b906
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PSYNTHDOWNLOAD, PSYNTHDOWNLOAD, PSYNTHDOWNLOAD structure pointer [Audio Devices], SYNTHDOWNLOAD, SYNTHDOWNLOAD structure [Audio Devices], _SYNTHDOWNLOAD, aud-prop_dbafbabb-05b5-4bf4-9791-e7c2eb78ed4f.xml, audio.synthdownload, dmusprop/PSYNTHDOWNLOAD, dmusprop/SYNTHDOWNLOAD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: Dmusprop.h
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
-	dmusprop.h
api_name:
-	SYNTHDOWNLOAD
product: Windows
targetos: Windows
req.typenames: SYNTHDOWNLOAD, *PSYNTHDOWNLOAD
---

# _SYNTHDOWNLOAD structure


## -description


The SYNTHDOWNLOAD structure specifies a handle for downloaded DLS data. It also specifies whether the buffer containing the DLS data can be freed.


## -struct-fields




### -field DownloadHandle

Handle to the downloaded DLS data buffer, which the miniport driver generates to uniquely identify the DLS data so that it can be unloaded later.


### -field Free

Specifies whether the client can free the data buffer as soon as the DLS download completes. If <b>TRUE</b>, the client can free the buffer when the download completes. If <b>FALSE</b>, the client must not free the buffer until it is unloaded. For more information, see the following Remarks section.


## -remarks



When processing a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537396">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a> get-property request, the synthesizer miniport driver uses the SYNTHDOWNLOAD structure to pass a handle back to the client. This handle uniquely identifies the downloaded DLS data. The client later specifies this same handle in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537398">KSPROPERTY_SYNTH_DLS_UNLOAD</a> set-property request that unloads the DLS data.

If the miniport driver makes its own copy of the DLS data, it sets the <i>Free</i> parameter to <b>TRUE</b> to indicate that the client can free the buffer containing the DLS data as soon as the KSPROPERTY_SYNTH_DLS_DOWNLOAD property request completes. If the miniport driver continues to use the client's copy of the DLS data, however, it sets <i>Free</i> to <b>FALSE</b> to indicate that the client should maintain its allocation of the original DLS data buffer until it unloads the data by sending a KSPROPERTY_SYNTH_DLS_UNLOAD property request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537396">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537398">KSPROPERTY_SYNTH_DLS_UNLOAD</a>
 

 

