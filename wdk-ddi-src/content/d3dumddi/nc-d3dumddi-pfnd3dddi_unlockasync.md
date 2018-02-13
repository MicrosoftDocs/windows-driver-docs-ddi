---
UID: NC:d3dumddi.PFND3DDDI_UNLOCKASYNC
title: PFND3DDDI_UNLOCKASYNC
author: windows-driver-content
description: The UnlockAsync function unlocks a resource or a surface within the resource that the LockAsync function previously locked.
old-location: display\unlockasync.htm
old-project: display
ms.assetid: 6af04c22-e559-4328-a20a-034b443fddc6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.unlockasync, UnlockAsync callback function [Display Devices], UnlockAsync, PFND3DDDI_UNLOCKASYNC, PFND3DDDI_UNLOCKASYNC, d3dumddi/UnlockAsync, UserModeDisplayDriver_Functions_f2270e47-4bf2-4486-8e6b-919daabd7c48.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	UnlockAsync
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UNLOCKASYNC callback


## -description


The <i>UnlockAsync</i> function unlocks a resource or a surface within the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function previously locked.


## -prototype


````
PFND3DDDI_UNLOCKASYNC UnlockAsync;

__checkReturn HRESULT APIENTRY UnlockAsync(
  _In_       HANDLE                hDevice,
  _In_ const D3DDDIARG_UNLOCKASYNC *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to a display device (that is, the graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlockasync.md">D3DDDIARG_UNLOCKASYNC</a> structure that describes the resource or surface within the resource to unlock.


## -returns



<i>UnlockAsync</i> returns one of the following values:

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
The resource is successfully unlocked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>UnlockAsync</i> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The resource that <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlockasync.md">D3DDDIARG_UNLOCKASYNC</a> describes was not locked by a previous call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function. 

</td>
</tr>
</table>
 




## -remarks



A user-mode display driver should call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function with the appropriate allocation handle after the <i>UnlockAsync</i> function is called. 

A user-mode display driver optionally implements <i>UnlockAsync</i>; the Microsoft Direct3D runtime calls <i>UnlockAsync</i> only if the driver implements the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>, <i>UnlockAsync</i>, and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a> functions. 

Like <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>, <i>UnlockAsync</i> is called on the main application thread while most other calls to the user-mode display driver functions are made on a worker thread (on multiple-processor computers). 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the <b>DriverVersion</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function), the Direct3D runtime will call <i>UnlockAsync</i> in a reentrant manner. When the runtime calls <i>UnlockAsync</i> in a reentrant manner, one thread can execute inside <i>UnlockAsync</i> while another thread that references the same display device executes inside of another user-mode display driver function. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlockasync.md">D3DDDIARG_UNLOCKASYNC</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UNLOCKASYNC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

