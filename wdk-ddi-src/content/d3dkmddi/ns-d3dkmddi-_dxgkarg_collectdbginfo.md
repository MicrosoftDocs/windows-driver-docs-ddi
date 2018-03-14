---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO
title: "_DXGKARG_COLLECTDBGINFO"
author: windows-driver-content
description: The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.
old-location: display\dxgkarg_collectdbginfo.htm
old-project: display
ms.assetid: f0dd72b5-9ab4-4511-b913-b0e456ea8950
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_COLLECTDBGINFO, DXGKARG_COLLECTDBGINFO structure [Display Devices], DmStructs_c3c19a4c-8536-474b-bca4-8b5af32fc4c8.xml, VIDEO_ENGINE_TIMEOUT_DETECTED, VIDEO_TDR_TIMEOUT_DETECTED, _DXGKARG_COLLECTDBGINFO, d3dkmddi/DXGKARG_COLLECTDBGINFO, display.dxgkarg_collectdbginfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_COLLECTDBGINFO
product: Windows
targetos: Windows
req.typenames: DXGKARG_COLLECTDBGINFO
---

# _DXGKARG_COLLECTDBGINFO structure


## -description


The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.


## -syntax


````
typedef struct _DXGKARG_COLLECTDBGINFO {
  UINT                       Reason;
  VOID                       *pBuffer;
  SIZE_T                     BufferSize;
  DXGKARG_COLLECTDBGINFO_EXT *pExtension;
} DXGKARG_COLLECTDBGINFO;
````


## -struct-fields




### -field Reason

[in] The <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug-check code</a> for which to return debug information in the buffer that <b>pBuffer</b> points to. These are possible values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VIDEO_TDR_TIMEOUT_DETECTED"></a><a id="video_tdr_timeout_detected"></a><dl>
<dt><b>VIDEO_TDR_TIMEOUT_DETECTED</b></dt>
<dt>0x117</dt>
</dl>
</td>
<td width="60%">
A <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> operation has reset a logical adapter.

</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_ENGINE_TIMEOUT_DETECTED"></a><a id="video_engine_timeout_detected"></a><dl>
<dt><b>VIDEO_ENGINE_TIMEOUT_DETECTED</b></dt>
<dt>0x141</dt>
</dl>
</td>
<td width="60%">
A <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> operation has reset one or more nodes within a physical adapter.

Available starting in Windows 8.

</td>
</tr>
</table>
 


### -field pBuffer

[out] A pointer to a buffer that receives the debug information that <b>Reason</b> specifies.


### -field BufferSize

[in] The maximum size, in bytes, to copy to the buffer that <b>pBuffer</b> points to.


### -field pExtension

[out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md">DXGKARG_COLLECTDBGINFO_EXT</a> structure that is allocated by the operating system and that the driver optionally populates with debug extension information.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md">DXGKARG_COLLECTDBGINFO_EXT</a>



 

 


