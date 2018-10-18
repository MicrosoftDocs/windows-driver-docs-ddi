---
UID: NC:d3dumddi.PFND3DDDI_DRAWTRIPATCH
title: PFND3DDDI_DRAWTRIPATCH
author: windows-driver-content
description: The DrawTriPatch function draws a new or cached triangular patch or updates the specification of a previously defined patch.
old-location: display\drawtripatch.htm
tech.root: display
ms.assetid: 98e5f2c5-2795-4226-b5c0-9498b37c22df
ms.date: 5/10/2018
ms.keywords: DrawTriPatch, DrawTriPatch callback function [Display Devices], PFND3DDDI_DRAWTRIPATCH, PFND3DDDI_DRAWTRIPATCH callback, UserModeDisplayDriver_Functions_a4fb7bb1-ec56-45a9-9cca-5be7bd9f4746.xml, d3dumddi/DrawTriPatch, display.drawtripatch
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DrawTriPatch
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DRAWTRIPATCH callback function


## -description


The <b>DrawTriPatch</b> function draws a new or cached triangular patch or updates the specification of a previously defined patch.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *


*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543070">D3DDDIARG_DRAWTRIPATCH</a> structure that describes the triangular patch to draw.


### -param *

*pInfo* [in]

Optional. A pointer to a D3DDDITRIPATCH_INFO structure that describes information about the triangular patch.


### -param *

*pPatch* [in]

Optional. A pointer to a buffer that contains three floating-point values (D3DFLOAT[3]) that provide the segment counts for each of the three edges of the triangular patch.


## -returns



<b>DrawTriPatch</b> returns S_OK or an appropriate error result if the triangular patch is not successfully drawn.




## -remarks



When the Microsoft Direct3D runtime calls the user-mode display driver's <b>DrawTriPatch</b> function, it can optionally supply information in the <i>pInfo</i> and <i>pPatch</i> parameters. The runtime sets flags in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543070">D3DDDIARG_DRAWTRIPATCH</a> structure that is specified by <i>pData</i> to indicate if it supplies this optional information. 

The runtime supplies a UINT value in the <b>Handle</b> member of D3DDDIARG_DRAWTRIPATCH to refer to the patch surface. Whenever the runtime redraws the patch surface, it passes the patch handle value and is not required to re-specify the D3DDDITRIPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information. Therefore, subsequent calls to the driver's DrawTriPatch function that use the same patch handle value run more efficiently.

The actual value in <b>Handle</b> is determined by the application and is not under runtime control. Therefore, the driver must handle any value that can be specified by a UINT. 

The special <b>Handle</b> value of zero indicates that the patch is dynamic; therefore, the driver cannot precompute or cache information for the patch. A nonzero value for <b>Handle</b> indicates that the patch is static (or updated with low frequency); therefore, the driver can precompute and cache information for the patch.

The driver must handle the following scenarios in its <b>DrawTriPatch</b> function: 

<ul>
<li>
If the <b>Handle</b> member is zero, the patch is dynamic. The driver should neither precompute nor cache information for the patch. In this situation, the runtime passes a pointer to a D3DDDITRIPATCH_INFO structure in the <i>pInfo</i> parameter and sets the RTPATCHFLAG_HASINFO flag in the <b>Flags</b> member of the D3DDDIARG_DRAWTRIPATCH structure to indicate the presence of the D3DDDITRIPATCH_INFO structure at <i>pInfo</i>. Optionally, the runtime can also set the RTPATCHFLAG_HASSEGS flag in <b>Flags</b> to indicate the presence of the segment information that is specified the <i>pPatch</i> parameter. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has not been previously specified in an earlier call to the driver's <b>DrawTriPatch</b> function, the runtime draws a new cacheable patch. The driver should allocate memory to store cached data and should add this data to its patch handle table. Because the runtime has not previously drawn this patch, the runtime should set the RTPATCHFLAG_HASINFO flag and pass a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter. The driver must check for the RTPATCHFLAG_HASINFO flag to verify the presence of the patch information. If no patch information is specified, the driver should ignore the <b>DrawTriPatch</b> call and should not allocate memory for cached data in its patch handle table. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawTriPatch</b> function and the RTPATCHFLAG_HASINFO flag is set, the runtime updates the definition for the patch. The runtime passes a pointer to a D3DDDITRIPATCH_INFO structure in the <i>pInfo</i> parameter, and the driver must recompute and recache the patch information. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawTriPatch</b> function and the RTPATCHFLAG_HASINFO flag is not set, the runtime redraws the patch. The driver should use the cached information to draw the patch. In this situation, the driver ignores the current vertex streams and the cached information is used instead. However, the runtime can still specify new segment information; therefore, the driver should check for the RTPATCHFLAG_HASSEGS flag and handle specified segment information even if it uses a cached patch.

</li>
</ul>
The driver receives notification to release cached patch information through the D3DRS_DELETERTPATCH render state. The value of this render state is the patch to delete.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543070">D3DDDIARG_DRAWTRIPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

