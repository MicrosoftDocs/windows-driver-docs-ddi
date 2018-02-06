---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEVICE
title: PFND3D10DDI_CREATEDEVICE
author: windows-driver-content
description: The CreateDevice(D3D10) function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice_d3d10_.htm
old-project: display
ms.assetid: c69eedb1-c975-412c-aa9f-cf64a702f937
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createdevice_d3d10_, CreateDevice callback function [Display Devices], CreateDevice, PFND3D10DDI_CREATEDEVICE, PFND3D10DDI_CREATEDEVICE, d3d10umddi/CreateDevice, UserModeDisplayDriverDx10_Functions_4d3d9d4c-e03b-46a9-a62a-cb49f071c0a2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CreateDevice
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CREATEDEVICE callback


## -description


The <b>CreateDevice(D3D10)</b> function creates a graphics context that is referenced in subsequent calls. 


## -prototype


````
PFND3D10DDI_CREATEDEVICE CreateDevice;

HRESULT APIENTRY CreateDevice(
          D3D10DDI_HADAPTER        hAdapter,
  _Inout_ D3D10DDIARG_CREATEDEVICE *pCreateData
)
{ ... }
````


## -parameters




### -param D3D10DDI_HADAPTER



### -param *






#### - hAdapter

 A handle to the graphics adapter object that was created with the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a> function.


#### - pCreateData [in, out]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.


## -returns


<b>CreateDevice(D3D10)</b> returns one of the following values:
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
The graphics context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DXGI_STATUS_NO_REDIRECTION</b></dt>
</dl>
</td>
<td width="60%">
The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> could not allocate the memory that was required for it to complete.

</td>
</tr>
</table> 



## -remarks


A display device is a graphics context that is used to hold a collection of rendering state. The same process can create multiple devices on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.

Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

