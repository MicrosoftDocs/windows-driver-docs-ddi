---
UID: NC:d3dumddi.PFND3DDDI_CREATEQUERY
title: PFND3DDDI_CREATEQUERY
author: windows-driver-content
description: The CreateQuery function creates driver-side resources for a query that the Microsoft Direct3D runtime subsequently issues for processing.
old-location: display\createquery.htm
old-project: display
ms.assetid: ac63b77b-2704-4d5b-bf1d-9d85e8a1e336
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreateQuery, CreateQuery callback function [Display Devices], PFND3DDDI_CREATEQUERY, PFND3DDDI_CREATEQUERY callback, UserModeDisplayDriver_Functions_b398e152-6530-4dcb-9665-ef45ad3d985b.xml, d3dumddi/CreateQuery, display.createquery
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	CreateQuery
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEQUERY callback function


## -description


The <b>CreateQuery</b> function creates driver-side resources for a query that the Microsoft Direct3D runtime subsequently issues for processing.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542958">D3DDDIARG_CREATEQUERY</a> structure that identifies the query.


## -returns



<b>CreateQuery</b> returns one of the following values:

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
The query is successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The Direct3D runtime calls the user-mode display driver's <b>CreateQuery</b> function with a query type to create resources for a query. The user-mode display driver creates the following resources for query types:

<ul>
<li>
BOOL for D3DDDIQUERYTYPE_EVENT. Before responding about an event, the driver must ensure that the graphics processing unit (GPU) is finished processing all of the operations that are related to the event. That is, the driver responds about an event after the issue end state occurs. The driver must always set the event's BOOL value to <b>TRUE</b> when responding. 

</li>
<li>
UINT for D3DDDIQUERYTYPE_OCCLUSION. The driver sets this UINT variable to the number of pixels for which the z-test passed for all of the primitives between the beginning and end states of the issue query. If the depth buffer is multisampled, the driver determines the number of pixels from the number of samples. However, if the display device is capable of z-test accuracy for each multisample, the conversion to number of pixels should generally be rounded up. An application can then check the occlusion result against 0, to effectively mean "fully occluded." Drivers that convert multisampled quantities to pixel quantities should detect render target multisampling changes and continue to compute the query results appropriately.

</li>
<li>
A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544294">D3DDDIDEVINFO_VCACHE</a> structure for D3DDDIQUERYTYPE_VCACHE. The driver responds after the issue end state occurs.

</li>
</ul>
For more information about issue query states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544575">D3DDDI_ISSUEQUERYFLAGS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542958">D3DDDIARG_CREATEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544294">D3DDDIDEVINFO_VCACHE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544575">D3DDDI_ISSUEQUERYFLAGS</a>
 

 

