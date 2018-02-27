---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCHINDIRECT
title: PFND3D11DDI_DISPATCHINDIRECT
author: windows-driver-content
description: The DispatchIndirect function executes the compute shader.
old-location: display\dispatchindirect.htm
old-project: display
ms.assetid: 0c818515-163f-48ba-ad57-f4405672c98f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DispatchIndirect, DispatchIndirect callback function [Display Devices], PFND3D11DDI_DISPATCHINDIRECT, UserModeDisplayDriverDx11_Functions_39c7b613-66de-4dd8-8b43-d1ae2a926e77.xml, d3d10umddi/DispatchIndirect, display.dispatchindirect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DispatchIndirect is supported beginning with the Windows 7 operating system.
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
-	DispatchIndirect
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_DISPATCHINDIRECT callback


## -description


The <b>DispatchIndirect</b> function executes the compute shader.


## -prototype


````
PFND3D11DDI_DISPATCHINDIRECT DispatchIndirect;

VOID APIENTRY DispatchIndirect(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hBufferForArgs,
  _In_ UINT               AlignedByteOffsetForArgs
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRESOURCE


### -param UINT








#### - AlignedByteOffsetForArgs [in]

 The offset, in bytes, into the buffer that <i>hBufferForArgs</i> specifies. <i>AlignedByteOffsetForArgs</i> must be a multiple of 4.


#### - hBufferForArgs [in]

 A handle to a buffer that contains three UINT values that hold the sizes, in thread groups, of the X, Y, and Z dimensions of the thread-group grid. The buffer contains the following tightly packed structure:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct DispatchArgs {
  UINT ThreadGroupCountX; 
  UINT ThreadGroupCountY;
  UINT ThreadGroupCountZ;
}</pre>
</td>
</tr>
</table></span></div>

#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The DispatchIndirect function performs the same task as the call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatch.md">Dispatch</a> function. The Direct3D runtime calls the driver's <b>DispatchIndirect</b> function on the display device to execute the compute shader over a number of threads in a grid of thread groups. However, <b>DispatchIndirect</b> obtains the number of thread groups to execute from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies.  <b>DispatchIndirect</b> reads three UINT values, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DispatchIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatch.md">Dispatch</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_DISPATCHINDIRECT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

