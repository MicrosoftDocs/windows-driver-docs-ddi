---
UID: NC:d3d10umddi.PFND3D10_2DDI_GETSUPPORTEDVERSIONS
title: PFND3D10_2DDI_GETSUPPORTEDVERSIONS
author: windows-driver-content
description: The GetSupportedVersions function queries for the Direct3D interface versions that the driver supports.
old-location: display\getsupportedversions.htm
old-project: display
ms.assetid: b38683f3-42f2-4f5e-9482-f72e9f2e0a34
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: GetSupportedVersions, GetSupportedVersions callback function [Display Devices], PFND3D10_2DDI_GETSUPPORTEDVERSIONS, PFND3D10_2DDI_GETSUPPORTEDVERSIONS callback, UserModeDisplayDriverDx11_Functions_065e47e6-c02d-4091-b614-a93aa834cbfb.xml, d3d10umddi/GetSupportedVersions, display.getsupportedversions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h, Prdrvcom.h
req.target-type: Desktop
req.target-min-winverclnt: GetSupportedVersions is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	GetSupportedVersions
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10_2DDI_GETSUPPORTEDVERSIONS callback function


## -description


The <i>GetSupportedVersions</i> function queries for the Direct3D interface versions that the driver supports. 


## -parameters




### -param Arg1


### -param *puEntries [in, out]

A pointer to a variable that, on input, contains the number of entries that the <i>pSupportedDDIInterfaceVersions</i> array should return and, on output, the number of entries that the <i>pSupportedDDIInterfaceVersions</i> array actually returns. 


### -param *pSupportedDDIInterfaceVersions [out, optional]

 A pointer to a block of memory that receives the array of Direct3D interface versions that the driver supports.


#### - hAdapter [in]

 A handle that identifies the graphics adapter. 


## -returns



<i>GetSupportedVersions</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The capabilities are successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetSupportedVersions</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>
 




## -remarks



When the Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/6f058f81-4cce-40c5-95a9-c0b717cf2bae">OpenAdapter10_2</a> function, the <b>Interface</b> and <b>Version</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a> structure contain the DDI version that the runtime uses to instantiate the driver. The driver can completely ignore these members. The driver can instead return capabilities and version information out through its <i>GetSupportedVersions</i> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541900">D3D10_2DDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/6f058f81-4cce-40c5-95a9-c0b717cf2bae">OpenAdapter10_2</a>
 

 

