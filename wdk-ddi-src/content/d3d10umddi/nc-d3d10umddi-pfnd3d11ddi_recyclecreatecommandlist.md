---
UID: NC:d3d10umddi.PFND3D11DDI_RECYCLECREATECOMMANDLIST
title: PFND3D11DDI_RECYCLECREATECOMMANDLIST
author: windows-driver-content
description: The RecycleCreateCommandList function creates a command list and makes a previously unused DDI handle completely valid again.
old-location: display\recyclecreatecommandlist.htm
old-project: display
ms.assetid: c387545e-2891-401d-b7ca-ee7549a52603
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D11DDI_RECYCLECREATECOMMANDLIST, RecycleCreateCommandList, RecycleCreateCommandList callback function [Display Devices], UserModeDisplayDriverDx11_Functions_ae724488-211a-4590-abcc-f2c8f954531e.xml, d3d10umddi/RecycleCreateCommandList, display.recyclecreatecommandlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCreateCommandList is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	RecycleCreateCommandList
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_RECYCLECREATECOMMANDLIST callback


## -description


The <i>RecycleCreateCommandList</i> function creates a command list and makes a previously unused DDI handle completely valid again.


## -prototype


````
PFND3D11DDI_RECYCLECREATECOMMANDLIST RecycleCreateCommandList;

HRESULT APIENTRY RecycleCreateCommandList(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_ const D3D11DDIARG_CREATECOMMANDLIST *pCreateCommandList,
  _In_       D3D11DDI_HCOMMANDLIST         hCommandList,
  _In_       D3D11DDI_HRTCOMMANDLIST       hRTCommandList
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D11DDI_HCOMMANDLIST


### -param D3D11DDI_HRTCOMMANDLIST








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateCommandList [in]

 [in] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createcommandlist.md">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to create a command list.  


#### - hCommandList [in]

 A handle to the driver's private data for the command list. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a> function. The handle is just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its command list. 


#### - hRTCommandList [in]

 A handle to the command list that the driver should use, when it calls back into the Direct3D runtime. 


## -returns



<i>RecycleCreateCommandList</i> returns one of the following values:

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
The command list is successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>RecycleCreateCommandList</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The driver is only required to implement <i>RecycleCreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability, which can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCreateCommandList</i>, see <a href="https://msdn.microsoft.com/7bede247-680d-4fd3-a10b-6ef63f0a88ec">Optimization for Small Command Lists</a>.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createcommandlist.md">D3D11DDIARG_CREATECOMMANDLIST</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_RECYCLECREATECOMMANDLIST callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

