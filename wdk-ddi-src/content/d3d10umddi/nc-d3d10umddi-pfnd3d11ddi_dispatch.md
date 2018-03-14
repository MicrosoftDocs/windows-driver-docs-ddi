---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCH
title: PFND3D11DDI_DISPATCH
author: windows-driver-content
description: The Dispatch function executes the compute shader.
old-location: display\dispatch.htm
old-project: display
ms.assetid: 6fbbf05a-efb0-4f24-8811-b87141cf2daa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Dispatch, Dispatch callback function [Display Devices], PFND3D11DDI_DISPATCH, UserModeDisplayDriverDx11_Functions_1b4b62fc-3cc5-4506-9a61-30ee65f8ffcd.xml, d3d10umddi/Dispatch, display.dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Dispatch is supported beginning with the Windows 7 operating system.
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
-	Dispatch
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_DISPATCH callback


## -description


The <b>Dispatch</b> function executes the compute shader.


## -prototype


````
PFND3D11DDI_DISPATCH Dispatch;

VOID APIENTRY Dispatch(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             ThreadGroupCountX,
  _In_ UINT             ThreadGroupCountY,
  _In_ UINT             ThreadGroupCountZ
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param UINT








#### - ThreadGroupCountX [in]

 The size, in thread groups, of the x-dimension of the thread-group grid.  The maximum size is 65535. 


#### - ThreadGroupCountY [in]

 The size, in thread groups, of the y-dimension of the thread-group grid.  The maximum size is 65535. 


#### - ThreadGroupCountZ [in]

 The size, in thread groups, of the z-dimension of the thread-group grid.  The maximum size is 65535. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The Direct3D runtime calls the driver's <b>Dispatch</b> function on the display device to execute the compute shader.  A compiled compute shader defines the set of instructions to execute per thread and the number of threads to run per group.  The thread-group parameters (<i>ThreadGroupCountX</i>, <i>ThreadGroupCountY</i>, and <i>ThreadGroupCountZ</i>) indicate how many thread groups to execute. Each thread group contains the same number of threads, as defined by the compiled compute shader.  The thread groups are organized in a three-dimensional grid. The total number of thread groups that the compiled compute shader executes is determined by the following calculation:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ThreadGroupCountX * ThreadGroupCountY * ThreadGroupCountZ</pre>
</td>
</tr>
</table></span></div>
In particular, if any of the values in the thread-group parameters are 0, the <b>Dispatch</b> function does nothing.  

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>Dispatch</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_DISPATCH callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

