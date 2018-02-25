---
UID: NC:d3dumddi.PFND3DDDI_UNLOCK
title: PFND3DDDI_UNLOCK
author: windows-driver-content
description: The Unlock function unlocks a resource or a surface within the resource that was previously locked by the Lock function.
old-location: display\unlock.htm
old-project: display
ms.assetid: 23cc9c64-99d4-4602-a1b0-234fe7fcc3da
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3DDDI_UNLOCK, Unlock, Unlock callback function [Display Devices], UserModeDisplayDriver_Functions_20b0d6f7-4bda-4d0f-9c3a-27d4011d2591.xml, d3dumddi/Unlock, display.unlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Universal
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
-	Unlock
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UNLOCK callback


## -description


The <i>Unlock</i> function unlocks a resource or a surface within the resource that was previously locked by the <i>Lock</i> function.


## -prototype


````
PFND3DDDI_UNLOCK Unlock;

__checkReturn HRESULT APIENTRY Unlock(
  _In_       HANDLE           hDevice,
  _In_ const D3DDDIARG_UNLOCK *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlock.md">D3DDDIARG_UNLOCK</a> structure that describes the resource or surface within the resource to unlock.


## -returns



<i>Unlock</i> returns one of the following values:

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
<i>Unlock</i> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The resource that <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlock.md">D3DDDIARG_UNLOCK</a> describes was not locked by a previous call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function. 

</td>
</tr>
</table>
 




## -remarks



These comments are analogous to the description in the Remarks section of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> reference page.

The user-mode display driver must call the Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function after <i>Unlock</i> is called. In this <b>pfnUnlockCb</b> call, the user-mode display driver passes an allocation handle. Before calling <b>pfnUnlockCb</b>, the user-mode display driver must first map the surface to an appropriate allocation. 

The runtime calls the user-mode display driver's <i>Unlock</i> function to unlock preallocated system memory surfaces as well. The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlock.md">D3DDDIARG_UNLOCK</a> structure that is pointed to by <i>pData</i> to differentiate <i>Unlock</i> calls that unlock preallocated system memory from other <i>Unlock</i> calls. If the user-mode display driver's <i>Lock</i> function called <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> to lock the system memory allocation that corresponds to the surface, it must also call <b>pfnUnlockCb</b>. Not calling <b>pfnUnlockCb</b>  stops the coordination between the runtime, the user-mode display driver, and the display miniport driver. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlock.md">D3DDDIARG_UNLOCK</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UNLOCK callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

